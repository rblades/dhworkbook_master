# Glitching Files

Glitching files messses with our expectations of what digital data should be. There is actually quite a large body of literature on the why and how of glitching ([try Glitch's GitHub for a place to start](https://github.com/GlitchTools/Glitch-Arts-Resources#writings)). For us as digital historians, glitching digital images or other documents reminds of us the ephemerality of digital data. It might also raise other questions about the composition of historical photography, and the ways that no image is an objective record of the past. In the exercise below, you build on what you learned about APIs and Regex to download images from the Open Context repository of archaeological data. Then, you use a script that will perform the same manipulations on every image in your folder. Finally, you will use another script to create a static website with all of your images, a gallery of glitch.

Spend some time on the articles and resources curated on [Glitch's GitHub](https://github.com/GlitchTools/Glitch-Arts-Resources) to begin to explore the philosophy and aesthetic of Glitch.

## Workflow we're going for:

1. Get images from Open Context (`ocget.sh`)
2. Glitch them (`do-glitch.sh`)
3. Make a website out of them (`expose`)
4. Push them to github Pages (`git`)

## Open Context

Open Context publishes archaeological data on the web. Archaeology generates vast amounts of information, both through excavation and through analysis. Open Context exists to publish curated versions of this data with unique digital object identifiers so that the source data of archaeology can be re-examined and re-studied in the future. Archaeology, uniquely amongst the historical disciplines, tends to destroy its subject matter, so reproducibility and open access data are extremely important issues. At [Open Context's API page](https://opencontext.org/about/services), they explain how to programmatically obtain information from their site. 

1. Check out [this example search on Open Context](https://opencontext.org/media-search/.json?prop=rel--oc-gen-cat-object||rel--oc-gen-cat-animal-bone&response=uri-meta&rows=10). Open that up, give it a play right now, and see what kinds of information exist. Try to craft a search that retrieves some interesting information.

    Once you've crafted a search that retrieves something of interest, it's time to build a script that will retrieve that information for you. Remember the exercise that queried the Canadiana api? Below I have modified that script to grab 10 records from the 'animal bone' category on Open Context. You could use that as a basis for your own search.

2. In DH Box, create a new folder with `mkdir` for this exercise, then `cd` into it. 

3. Open the nano editor and paste the script below in a new file. Make sure to read the comments, because there are a few lines you have to customize. (You'll get file not found errors if you don't pay attention!) 

    The line beginning with 'sed' searches for the `thumbnail` key, and marks it off with a tilde. The `|` character is called a 'pipe' and it pipes the output of the command before it into the input of the command after it. The first pipe passes the output of that first sed command to grep, which finds the lines marked with the tilde to the tr (trim) command, which then deletes all of the other information; the next pipe passes to a series of sed commands which then get rid of whitespace and the word thumbnail, the tilde, and any commas, leaving us with a list of direct URLs to the thumbnails.

    The wget command grabs each thumbnail in the list in turn, waiting 2 seconds between requests, and using a limited amount of bandwidth (we're good digital citizens, remember).

        #! /bin/bash
        # we already know how to ask the api for the infromation we're interested in, from studying opencontex.org' api documentation. Below we ask for a 10 records related to animal bones
        curl 'https://opencontext.org/media-search/.json?prop=rel--oc-gen-cat-object||rel--oc-gen-cat-animal-bone&response=uri-meta&rows=10' >> results.txt
        # the next two lines take the results.txt file that is quite messy and clean it up. I'll try to explain what they all mean. Basically, tr deletes a given character - so we delete quotation marks "\"" (the slash tells the computer not to treat the quotation mark as a computer code, but as a quotation mark itself), to erase spaces, and to find the phrase "key:" and delete it too.
        sed -r 's/(.+\bthumbnail\b.+)/~\1/g' results.txt | grep '~'| tr -d "\"" | tr -d "{" | tr -d "}" | tr -s " " | sed '/^\s*$/d' | tr -d ' ' | sed 's/\bthumbnail:\b//g' | sed 's/,//g' | sed 's/~//g'> thumbnailstograb.txt
        # gotta grab 'em all.
        # in the line below, put the full path to your images file, eg mine is home/shawngraham/oc/images. Yours might be home/yourname/oc/images
        wget -i thumbnailstograb.txt -P path/to/images --limit-rate=20k -w 2

4. Save it as `ocget.sh`, then use `$chmod 755 ocget.sh` to make it executable. 

5. Then `$ mkdir images` so you have a place to put the images into.

**Hey, images keep appearing even though I ctrl+c to stop the download** I hear some of you say. Well, that doesn't necessarily stop anything; when you ran the command, you started a **process** and it might still be ticking away in the background. If this seems to be happening to you, type `ps ux` to get a list of running processes. If wget is still running in the backround, you'll see it listed in the right-most column. The first number in that row is its PIDnumber; to kill it, type `kill -9 PIDnumber` where you swap in the actual PIDnumber.

**Also**, before you re-run this script, you need to delete the 'results.txt' file and the 'thumbnailstograb.txt' file, like so: `rm results.txt` etc. Otherwise, it'll just add your results to the end of the previous results, making your list longer and longer...

## An image glitch script in Python

The next step is to glitch the image. 

1. Go to [the bndr GitHub repository](https://github.com/Xpktro/bndr). This is a python package for mucking about the bits inside a jpg. 

2. Install it at the command line with `$ pip install bndr`.

3. Make a new folder for the output of this process: `mkdir out`.

    Now, this code is meant to be run on one file at a time, like this: `$ bndrimg photo-name.jpg `. Typing in each file name by hand would take a very long time to glitch everything. So instead, we write a little script that we'll call `do-glitch.sh`. 

4. In Nano, paste the following:

        #! /bin/bash
        # do-glitch.sh
        # run the glitch script on each image in the images folder
        for file in images/*.jpg; do bndrimg "$file"; done
        # move the glitched files to the output folder
        find ./ -name '*out.png' -exec cp -prv '{}' 'out/' ';'

    This isn't the most elegant script, but it works, and frankly, that's all that matters sometimes.

5. Change the permissions so we can run it by typing `$ chmod 755 do-glitch.sh`. This script reads each file name in the images folder, and passes them one at a time to the bndr command (you can't run it when you're **inside** the images folder, remember). Then, we move just the glitched images to the 'out' folder. 

6. Download some of the pics to your own machine using the filemanager to see your glitched art!

## A static website generator for photography

Finally, let's turn that folder of pictures into a website. We're going to use the Exposé site generator, which you can get from the [Exposé GitHub repository](https://github.com/Jack000/expose). Take a moment to read through the details of that package.

1. Use the `cd` command to get back up to your main directory (ie. don't do this when you're in your images folder). 

2. Grab the code:
    `$ git clone https://github.com/Jack000/Expose.git`

    The Exposé script relies on some helpers and so on in its folder. But we would like to be able to run that command no matter which folder we're in. We tell the computer that when we type `expose` we **actually** mean, the version that lives in that location where we just downloaded it. That is to say, we use the `alias` command. On my machine, it looks like this: `alias expose=/home/shawngraham/oc/Expose/expose.sh` 

    On your machine, it might be in a different location. Note also that the Expose repo is uppercase E, while the command is lowercase e. **also** every time you start a session, you'll need to do this alias command or else the computer won't know what you're talking about.

3. To generate the static site, cd into your `out` folder that holds your glitched images. 

4. At the prompt, type `$ expose`. 

    Ta da! You now have a fully functional website showing off your glitch art.

    You can customize it to use an alternative theme, a few bells and whistles; see the Expose documentation. One thing that you should do is to add captions for your images. You write these as either .txt or .md files, but make sure the file name for the caption is the same as for the image **and** put it in the same folder as the source images! You do this **before** you run the expose script. So `beaker-pic.png` would have as a caption file `beaker-pic.txt` or `beaker-pic.md`. You specify where the caption goes on the image in the YAML; that is, the metadata for your caption. So, if we opened 'beaker-pic.md' we might see,

        ---
        top: 30
        left: 5
        width: 30
        height: 20
        textcolor: #ffffff
        ---
        # A Picture of a Beaker
        Beakers were used to carry rare aromatic herbs and spices...

More possibilities for sorting out the position of the text are discussed in the Expose documentation.

## Host the site on github

You can push the code for your site to github, and then use github's gh-pages feature to serve it up as a live website! Expose creates all of the code for the website inside a new folder called `_site`.

1. Type `$ cd _site`
2. Turn this folder into a git repository: `git init`.
3. Go to your account on GitHub.com (in another browser window). Click on the `+` at the top-right to make a new repository. Call it whatever you want, but *do not* initialize it with a readme.
4. Back at the command line in your `_site` folder, type `$ git add .` This stages all of the files and subfolders for a new commit.
5. Type `$ git commit -m "first commit"` to make a commit message
6. Tell git where your remote repository is: `$ git remote add origin https://github.com/YOUR-ACCOUNT/YOUR-NEW-REPO-YOU-JUST-MADE.git`
7. Push your materials to GitHub: `$ git push -u origin master` (Git might ask for your account username and password)
8. Once that finishes, go back to GitHub and reload the page at https://github.com/YOUR-ACCOUNT/YOUR-NEW-REPO-YOU-JUST-MADE. You should see your changes.
9. On the button where it says 'Branch: Master', click on the down arrow. In the box where it says faintly 'Find or create a branch', type `gh-pages`. This is a special branch which tells GitHub, 'serve this up as actual code when the user goes to the special github.io version of github'.
10. Click on the gearwheel icon, to go to the settings page (You can also find it at https://github.com/YOUR-ACCOUNT/YOUR-NEW-REPO-YOU-JUST-MADE/settings). 
11. Scroll down to the box that says 'GitHub Pages'. 
12. In the green box, it says 'you're site is published at https://YOUR-ACCOUNT.github.io/YOUR-NEW-REPO-YOU-JUST-MADE'. 
13. Click on that link and you'll see your site! (Visit [my site on gh pages](https://shawngraham.github.io/exposetest/site/).)

## Conclusion

I see no reason why digital history cannot bleed into art. Art is meant to provoke, to prompt reflection, discussion, controversy. Glitching images confounds our expectation of what digital data are supposed to be, supposed to do. If you choose your pictures carefully, glitching can tell a story as profound as any essay.
