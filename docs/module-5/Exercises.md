# Capstone Exercise

For the Capstone Exercise, you have the opportunity to create a domain (website + complete access to the webserver that powers it, so that you can install other platforms/services) of your own. A typical setup will be something along the lines of:

1. GitHub: `yourusername.github.io`.
2. Reclaim Hosting: `your-domain-name.org` or `your-domain-name.ca` or `your-domain-name.com`.

On your blog/narrative, you may want an 'About' page where you can signal the kinds of history you're interested in, and the preferred way for people to get in touch with you. You do not have to use your real name. Remember the [real names policy](http://site.craftingdigitalhistory.ca/rubric-and-assessment.html#real-names-policy).

This section begins with several options you may wish to pursue for the Capstone Exercise. Following these options are resources, tutorials, and tips/hints you can reference to support the Capstone Exercise you choose. Depending on how you decided to communicate findings, this section contains resources which introduce you to the following concepts:

+ Layout
+ Manipulating graphics
+ Design with colour and font
+ Creating digital exhibits

I do not want to leave you thinking that all digital history work is necessarily text based. To that end, if you are looking for a challenge or for exposure to something rather different, I suggest you at least bookmark my [series of tutorials on augmented reality, games, and 3d models for history and archaeology](https://github.com/shawngraham/ar-archaeology/tree/master/workshop%20materials).

Let's get started.

![Image showing Ukrainian Parliament fist fight three times: 1 the original; 2 the photo with the Fibonnaci Golden spiral overlayed; 3 the photo as a Renaissance painting](http://uploads.neatorama.com/images/posts/587/74/74587/1407463055-0.jpg)

['Accidental Renaissance: the photos that look like Italian paintings'](http://www.theguardian.com/artanddesign/2014/aug/06/accidental-renaissance-photojournalism-italian-painting-ukraine-frank-lampard).

## Option 1: GitHub Pages with a Static Site Generator

Static site generators are software packages that allow you to quickly build and easily update a website via the terminal. Most static site generators use human readable programming languages like `YAML`/`YML` (Yet Another Markdown Language) that contain the settings for your website. You create a basic text file (i.e. Markdown), run a build command in the terminal that will convert your text files into web pages, and push the pages to your server. 

GitHub offers each user their own unique domain attached to their account - this service is called [GitHub Pages, or gh-pages](https://pages.github.com/). Each user domain resembles `yourusername.github.io`, where `yourusername` is your GitHub account username. If you went to `yourusername.github.io` right now, it will show a `404` / 'site not found' error. This is because you have not yet set-up your gh-pages website.

Like the `master` branch of your GitHub repository, `gh-pages` is another branch option. Essentially, you create a GitHub respository, populate the gh-pages branch with web files, and your `yourusername.github.io` will become a functioning website.

By deafault, GitHub Pages uses [Jekyll, a static site generator](https://jekyllrb.com/). However, Jekyll is not the only option. [Hugo](https://gohugo.io/) is another static site generator. This workbook was built using the [static site generator MKDocs](https://www.mkdocs.org/). While this option shows you how to use GitHub Pages powered by Jekyll to populate your GitHub domain, the instructions are generally similar for other static site generators. You make a few changes and run the website using a GitHub repository. 

1. Login to your GitHub account.
2. Click the button labelled `+` at the top left of the page next to your account.
3. Select `New repository`.
4. Under `Repository name *`, enter `yourusername.github.io` (ensure you change 'yourusername' to your GitHub username).
5. Click the button labelled `Create repository`.
6. Navigate to your DH Box account and open the terminal (you can also set this up on your own machine, in which case you open the Terminal (Mac) or Command Prompt (Windows) or GitHub desktop client).
7. Type `$ git clone https://github.com/username/username.github.io` into the terminal (changing the URL to your GitHub repository path).
8. Type `$ cd username.github.io` into the terminal (ensure you change 'username' to your GitHub username).
9. Type `$ echo "Hello World" > index.html` into the terminal. This will pipe "Hello World" into the home file `index.html` of your new site.
10. Type `$ git add --all` into the terminal.
11. Type `$ git commit -m "Initial commit"` into the terminal. 
12. Type `$ git push -u origin master` into the terminal.
13. Navigate to your domain at `yourusername.github.io`. You will see the text "Hello World".

### Customize your website

The instructions above showed you how to get you GitHub Pages domain up and running. GitHub provides further instruction on [customizing your Jekyll site in their documentation](https://help.github.com/en/articles/using-jekyll-as-a-static-site-generator-with-github-pages). GitHub Pages makes it easy to set-up a theme.

1. Navigate to your GitHub Pages repository.
2. Click the tab labelled `Settings`.
3. Scroll down to the section labelled `GitHub Pages`.
4. Click the button labelled `Change theme`.
5. Choose a new theme from the provided options.
6. Open the `_config.yml` file and and click the pen/pencil icon to edit the file.
7. Your configuration file will show only the theme information. Add the following `YAML` configuration settings to you `_config.yml` file:
    
        github: [metadata]
        encoding: UTF-8
        kramdown:
         input: GFM
         hard_wrap: false
        future: true
        jailed: false
        gfm_quirks: paragraph_end
    

8. Open the `index.html` file and and click the pen/pencil icon to edit the file.
9. Change the name of the file to `index.md`.
10. Remove the "Hello World" message and replace it with the following Markdown header:
    
    
        ---
        title: Home page
        layout: default
        ---

        Here is my home page.
        

11. Add a commit message and click the green button labelled `Commit changes`.
12. Navigate to your repository home page and create a new file called `2019-04-07-first-post.md` (change the `2019-04-07` to today's date).
13. Copy and paste the following text into your new Markdown file:

        ---
        title: This is my title
        layout: post
        ---

        Here is my page.

14. Add a commit message and click the green button labelled `Commit changes`.
15. Navigate to your `yourusername.github.io` domain. If the site has not updated yet, wait a minute and/or clear your browser's cache.

### Going Further

The instructions above show you how you can begin customizing you Jekyll website. You will probably want to change the theme and structure of the website. For instance, your blog posts should go in a folder called `_posts`. For more information, read [Barry Clark's article on customizing your Jekyll site](https://www.smashingmagazine.com/2014/08/build-blog-jekyll-github-pages/). You will also want to read through the [Jekyll documentation](https://jekyllrb.com/docs/).

Most static site generators use similar layouts, structures, and `YAML` configurations. While the documentation for each generator will differ, the general idea between all of them remains the same. 

You may also want to build a simple website through GitHub Pages using the MkDocs static site generator and DH Box. Navigate to the [static site generator exercise using GitHub Pages in the supporting materials](../supporting materials/gh-pages.md).

## Option 2: Jekyll Now

Jekyll is a static site generator widely used to create a website quickly that you can run from your GitHub account. Jekyll takes static Markdown files and converts them to a functioning website. While Jekyll requires some editing via the terminal, [Jekyll Now](https://github.com/barryclark/jekyll-now) is a project from [Barry Clark](https://github.com/barryclark) that allows you to leverage the blogging power and simplicity of Jekyll without touching the terminal. 

**NB** If you already have a gh-pages branch set up at `yourusername.github.io`, this may produce some unexpected results.  

1. Login to your GitHub account.
2. Navigate to the [Jekyll Now repository](https://github.com/barryclark/jekyll-now). For further instruction, follow the [Jekyll Now Quick Start guide on GitHub](https://github.com/barryclark/jekyll-now#quick-start).
3. Fork the Jekyll Now repository.
4. In your fork of the respository, click `Settings`.
5. Under `Repository name`, change the name from `jekyll-now` to `yourusername.github.io` (ensure you change 'yourusername' to your GitHub username). By setting the name to your unique GitHub domain (i.e. gh-pages), GitHub knows to make your gh-pages domain draw from these files.
6. Click the button labelled `Rename`. Your site is now available at `yourusername.github.io`. **NB** If you navigate to your domain URL right away, it will not be there and will show a '404' error. **You first need to upload a post in the format `YYYY-MM-DD-some-text.md`, ensuring `YYYY-MM-DD` is always the prefix to your posts file name.**
7. Navigate back to your forked repository page.
8. Open the `_config.yml` file.
9. Click the pen/pencil icon to edit the file.
10. Change the relevant fields (i.e. `name`, `description`, `avatar`, `footer-links`, etc.). For `avatar`, navigate to your GitHub profile, right click your profile picture/avatar, and select `View image`. This will open your avatar in a new tab. Copy the URL for your avatar and paste it into the `_config.yml` `avatar` section.
11. Write a commit message and click the green button labelled `Commit changes`. 
12. Navigate to the `_posts` folder and open the `2014-3-3-Hello-World.md` file.
13. Click the pen/pencil icon to edit the file.
14. Change the file name from `2014-3-3-Hello-World.md` to something relevant, ensuring to change the prefix to today's date in the `YYYY-MM-DD` format. 
15. Edit the file to describe your new site.
16. Write a commit message and click the green button labelled `Commit changes`. 
17. Navigate to `yourusername.github.io` (**remember**, ensure you change 'yourusername' to your GitHub username). You should now see your udpated site. If your site still shows a `404` error, try clearing your browser's cache and trying again. Also, ensure your post files use the proper naming convention with the ``YYYY-MM-DD`` date prefix. 
18. To add new posts, navigate to the `_posts` folder and click the button labelled `Create new file`. Remember to use the proper naming convention with the ``YYYY-MM-DD`` date prefix.

### Going Further

After following the instructions in the previous section, you now have a functioning website that runs entirely through GitHub. You can, however, further customize your site. Read through [Barry Clark's article on customizing your Jekyll site](https://www.smashingmagazine.com/2014/08/build-blog-jekyll-github-pages/). Incorporate design and functionality in your website from the resources on this page.

## Option 3: Reclaim Hosting

In the course space for cuLearn, I gave you a code to use to pay for a domain of your own. I have already purchased domain space for you from an academic web hosting service, [Reclaim Hosting](https://reclaimhosting.com/shared-hosting/). This space will last for one year, at which point you have the option of paying to renew it or letting it die. Previous students in this course have used their domain to help with their applications for jobs and graduate school.

Because you have complete access and control over your domain, you can install other services as well. For instance, maybe you use Dropbox or Google Drive to sync your files across machines, or to function as a backup? You can install a service called 'OwnCloud' on your own domain that does the same thing, so that you have control over all your own materials.

1. You will be asked for the name you want to have for your space. You need to be thinking of branding here. Think of a professional name that conveys something of your personality and approach to history. I for instance own the domain, 'Electric Archaeology', which I chose to convey that I'm interested in digital archaeology, but also, that I move fast and cover a lot of breaking develops in the field (Hey. It's my blog. I like the name). Please choose wisely. Some combination of your first and last name is often the best idea, since your own name is your own best calling card ('shawn graham' is such a generic name, that it was already long gone by the time I started doing digital history). Type in a name, select a top-level domain (ie. .com, .ca, .org, etc. I'll suggest .ca), and click on the 'check availability' button.
2. If the pop-up says 'Congratulations, domain available!' then click on the continue button. (You may be offered free id protection, where Reclaim Hosting will hide your details is someone does a 'who-is' search on the domain name. If it does, then tick off the check box to confirm that you want this, and hit continue).
3. On the next screen, (the billing screen) fill in all of the information. The balance should be $0. At the bottom left, it will also say that you’ve used a one-time promotional code. Hit the green button at the bottom to complete the purchase (which is not costing you anything).

Congratulations! You now own your very own domain. **It might take a bit of time for your domain to appear live on the web**. During this time, you can log into your cPanel and install Wordpress and so on - see the next section below.

Giving you a space of your own is my political act of protest against the centralization of learning inside learning management systems. Learning isn't 'managed', it's cultivated. Unlike cuLearn, I cannot monitor your activity inside your own domain. I can only see what you choose to make public. Unlike Facebook or Snapchat or Instagram, I am not trying to monetize your personality on the web.

### Wordpress for your blog

Wordpress is probably the best option for a platform for writing the narrative bits of your digital history work.

1. Click the 'Client area'. It will tell you that you have one active account (with Reclaim Hosting) and one active domain. When the time comes to renew your account or to close it down, this is where you do it. Note also that there is a link to 'Support', which will put you in touch with Reclaim Hosting's help desk. They are extremely fast and good at providing support; always treat any help request you make with them **as if** you were writing a formal email to me. Be polite and considerate, and thank them. The owners of the business often are the ones who provide the help! Without them, we couldn't do this class.
2. Go to 'cPanel' - this is where you can install all sorts of different kinds of software on your account. Search for and select 'Web applications'
3. Click on Wordpress. Then click on 'Install this application'.
4. The next screen presents you with a number of options. Leave these set to their defaults. For 'location', leave this blank (you want to leave the directory option blank). That tells the installatron to put Wordpress at `your-domain.ca`. (When/if you install other pieces of software, you'd change this variable so that the new software doesn't overwrite this software!)
5. Further down the page, under 'Settings', you need to change 'Administrator username', 'Administrator password', 'Website title', 'Website tagline'. **This is the username and password to actually do things with your blog, and the name of your blog itself**. Leave everything else alone.
6. Click Install!
7. Once it's done, the installer will remind you of the URL to your site, and the URL to the blog's dashboard (where you go to write posts, make changes to the look and feel of the site). Open these in a new browser window, and bookmark them. To login to your blog, remember to go to the dashboard URL (eg. `http://your-domain.ca/wp-admin`), enter your blog administrator username and password.
8. You can close the cPanel webpage now (log out first).

#### Customising your blog

If you look at the dashboard for your blog, you'll see a lot of options down the left side of your screen. If you want to change the look of your blog, click on 'Appearance' then click on 'Themes'. A number of themes are pre-installed. You can click on the different themes and select 'Preview' to see how your blog might look. When you find one you like, select 'activate'. Go to the other browser window where you have `your-domain.ca` open. Reload the page to see the changes take effect!

If you're the sort of person who likes to sketch ideas out on paper, Lauren Heywood of the [Disruptive Media Learning Lab](http://dmll.org.uk/) has designed a paper-based exercise to prototype ideas. Why not give it a try? [Print this PDF of Wordpress design (downloads in a new window)](http://coventry.domains/support/wp-content/uploads/staff-guide-to-plan-your-wordpress-site-with-paper.pdf) and follow the instructions.

To write new content, know that there is a difference between a **Post** and a **Page**. A **page** is a new link on your site, while **posts** appear in chronological order on a page, with the most recent on top. Most themes show the most recent post by default, and pages appear in any menus on the site. **When you are logged into your blog** any post or page will have an 'Edit' button at the bottom that you can click. You'll then be presented with an editing box with the standard toolbar across the top (allowing you to change the font, insert images, change the alignment of the text and so on). At the top right will be a button to save or publish/update the post/page.

Your blog will have a default 'about' page. Change that default text now to reflect something about who you are and why you are taking this course.

To create new pages, you click on the 'Pages' link in your dashboard and select 'Add new'.

To create new posts, you click on the 'Posts' link in  your dashboard and select 'Add new'.

Explore the options for your blog; customize and make the space your own.

**Password protected posts:** If for any reason you feel that you don't want a post to be viewable by the web-at-large, you can hide it behind a password. At the top right where the 'Publish' button hides, click on 'Visibility' and select 'Password protected'. Remember though: you'll have to share the password with me for grading purposes.

![Visibility Options in Wordpress](https://codex.wordpress.org/images/7/70/visibility.jpg)

For more information about controlling visibility of your posts and so on, [visit the Wordpress content visibility help page](https://codex.wordpress.org/Content_Visibility).

### Collecting your own annotations on your blog

Hypothes.is has an **API** that allows you to do some neat things. 'API' stands for 'Application Programming Interface', which is just a fancy way of saying, 'you can write a program that interacts with this web service'. [Kris Shaffer](http://pushpullfork.com/), a professor at the University of Mary Washington, has written a **plugin** for Wordpress that allows you to automatically collect annotations you make across the web and to display them all on a single page on your blog. So, we'll go get that plugin and install it on your blog:

Open [Kris Shaffer's Hypothes.is aggregator](https://github.com/kshaffer/hypothesis_aggregator) in a new browser window.

1. Click 'Clone or Download' (the green button at the top right).
2. In the pop-up, click 'Download ZIP'
3. Go over to the dashboard for your blog (if you closed this, you can get there again by opening a new browser window and going to `your-domain.ca/wp-admin`).
4. In the dashboard, click on Plugins >> Add New.
5. Click 'Upload Plugin'. It will open a window asking you to find and select the zip file you downloaded. This is probably in your 'Downloads' folder. Select and click Ok.
6. Once it’s uploaded and installed, click 'Activate'.
7. In the dashboard, click on 'pages' then add a new page. Call it 'Web Notes' or 'Annotations' or something similar.
8. Shaffer has created a 'shortcode' that tells Wordpress to go over to Hypothes.is and grab the latest information. So, in the text of your new page (in the editor window, make sure to click the 'text' button or else this won't work), enter the shortcode that will grab all of your public annotations: `[hypothesis user = 'kris.shaffer']` where you remove the `kris.shaffer` and put in your own Hypothes.is username.
9. Hit the 'Publish' button. Wordpress will report that the page has been published and give you a link to it; click on this link to see your new always-updating list of annotations! Of course, if you haven't made any public annotations yet, nothing will display. Go annotate something, then come back and reload the page, but remember to annotate using [our HIST3814o group](https://hypothes.is/groups/886ipqWe/hist3814o).

-----

## Layout

'Layout' can mean different things in different contexts. A general overview on issues in layout is covered by ['What makes a design great', Lynda.com (requires sign-up for free trial)](https://www.lynda.com/InDesign-tutorials/Introduction-Graphic-Design/633854-2.html) and ['Exploring principles of layout and composition' (requires sign-up for free trial)](https://www.lynda.com/Graphic-Design-tutorials/Exploring-principles-layout-composition/419419/534012-4.html). The [Slideshare on effective layouts](http://www.slideshare.net/kernlearningsolutions/what-is-an-effective-layout-3435438) gives you a sense of things to watch out for as well.

For academic posters in particular, consider [these poster design suggestions from the APA](http://www.apa.org/gradpsych/2011/01/poster.aspx).

In essence, good layout makes your argument legible, intuitive, and reinforces the rhetorical points you are trying to make. You should take into account 'principles of universal design' &mdash; consider design issues with [PowerPoint](http://accessproject.colostate.edu/udl/modules/powerpoint/mod_ppt.php) and [websites](http://accessproject.colostate.edu/udl/modules/html/mod_html.php) (although some of the technical solutions proposed in those two documents are a bit out of date, the general principles hold!).

If you decided to communicate findings via a poster, following are some hints/tips for designing a poster or modifying an existing poster.

### Inkscape

View the [Inkscape exercise in our supporting materials for a gentle introduction to the software](../supporting materials/inkscape.md).

1. Download one of the scientific poster templates from [Ugo Sangiorgi](https://github.com/ugosan/svg-conference-poster) (These are developed from [Felix Breuer's blog post](http://blog.felixbreuer.net/2010/10/24/poster.html); note his discussion on design). 
2. Open it in Inkscape. 
3. Make notes in your open notebook **from the point of view of layout:** what elements of the design work? What aren't working? How would you repurpose this poster to fit the requirements of the assessment exercise ([remember, the details in the syllabus](https://github.com/hist3907b-winter2015/syllabus/blob/master/exercise_assessment_guideline.md))?
4. Visit [Inkscape's website for help with the basics of Inkscape](https://inkscape.org/en/doc/tutorials/basic/tutorial-basic.html). 
5. Modify the poster, and upload the SVG, PDF, or PNG version to your repository.

### PowerPoint 

There's a lot of information out there on making posters with PowerPoint. 

1. Read [parts 1, 2, and 3 of the Make Signs tutorial](http://www.makesigns.com/tutorials/scientific-poster-parts.aspx) and then consider [Colin Purrington's advice](http://colinpurrington.com/tips/poster-design). Once you've read and digested the material, pick a poster from [Pimp My Poster](https://www.flickr.com/groups/pimpmyposter/pool/) that sticks out to you. 
2. Make notes in your open notebook: **from the point of view of layout** what elements of the design work? What aren't working? How would you repurpose this poster to fit the requirements of the assessment exercises ([remember to visit GitHub for the details](https://github.com/hist3907b-winter2015/syllabus/blob/master/exercise_assessment_guideline.md))? 
3. Grab a template from [from Colin Purrington's website](http://colinpurrington.com/tips/poster-design#templates), and use it to prototype a poster that works. 
4. Upload the poster as a PDF to your repository.

If you want to explore layout in the context of webpage creation, I would point you to the the roster of lessons at [Codeacademy](https://www.codecademy.com/catalog/subject/web-development). Same instructions: find an existing site that you will consider from the point of view of what works, what doesn't, and use that reflection to guide the construction of your own.
_____

## Typography

Typography plays an important role in visual communication. It can do everything from reduce eyestrain (do a search for 'easiest fonts to read on screen') to communicate power and authority. Is it any wonder that strong bold capitals come to be known as 'Roman'? But first: [are you a comic sans criminal?](http://www.comicsanscriminal.com/)

**NB** Serif fonts are **sometimes** not as accessible as sans-serif fonts. Older screens and monitors can have a difficult time rendering serif fonts. Sans-serif fonts can be more readable across different screens. **However**, this does not mean you should throw away serif fonts &mdash; many serif fonts can be quite accessible and add to your design goals if used properly. For more information on accessible fonts, check out [WebAIM's article on the topic](https://webaim.org/techniques/fonts/).

If you decided to communicate findings via a poster, website, or anything involving design, below are some hints/tips for the proper use of typography: 

+ I want you to read and understand the section on [font choices from the Owl at Purdue](https://owl.english.purdue.edu/owl/resource/705/01/).
+ Then, play some rounds of [Typeconnection](http://www.typeconnection.com/index.php). Pay attention to why &mdash; or why not &mdash; various pairings work.
+ Then, I want you to consider what typographic pair would work best for the Capstone Exercise? 
+ Finally, the following tutorial shows how you can make a webpage that uses your paired fonts and explains why they work.

The first part of this section then is to find a pair of fonts and to understand why they work best for you. 

1. Read the materials above, and once you're done with the [Typeconnection site](http://www.typeconnection.com/index.php), go to [Google Fonts](https://www.google.com/fonts) and search for a pair that are **suitable for your purpose**. 

2. When you find a font you like, click the 'Add to collection' button.

3. At the bottom of the screen, you'll see a link for 'use'. Click on this &mdash; Google will ask you if you want to use any of the variants of the font. Tick off accordingly. 

4. Do you see the embed code that Google provides, and the code to integrate the font into your CSS (stylesheet)? Leave this window open &mdash; we're going to use it in a moment.

5. Make a new repository on GitHub. 

6. In your repository, click the button beside 'branch'. 

7. In the search box that opens, type in ```gh-pages```. This will create a version of your repository that can be served as a website. You're now in the gh-pages branch.

8. Click on the + sign (plus sign) beside the repository name. This will create a new file in your gh-branch of your repository. Call it ```myfontchoice.html``` (the `.html` file name is important to specify; otherwise your browser will not know how to render your page).

9. You now need to put some HTML in there. I've written a simple webpage that will use two fonts from Google Fonts, and then applies the font to my text depending on whether or not it is a header, which you specify like this: ```<h1> this is a header in between header tags </h1>``` or a paragraph, which you specify like this: ```<p>blah blah blah a paragraph of text blah blah blah</p>```. Right-click and open in a new tab [my webpage on GitHub](https://raw.githubusercontent.com/hist3907b-winter2015/module5-humanitiesvisualization/master/fontexample.html). Copy the HTML into your new HTML document. Commit your changes (ie. save).

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/QQuHjgVqEQ4?rel=0" title="Creating a GitHub web page" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

10. Let's see what we've got. To see the website version of your gh-pages branch, you go to ```<yourusername>.github.io/<reponame>/myfontchoice.html``` (ie. the final part of the URL is the name of the document in your repo). Do that now. You should see a simple webpage, with two very distinctive fonts.

11. Now let's slide your font choices into the HTML. Go to your HTML page in your gh-pages repo (ie. not the ```github.io``` version, but the ```github.com/<yourusername>/<repo>/myfontchoice.html``` version). 

12. Hit the edit button. Look closely at line 6. Do you see my two fonts? Do you see the pipe character (the `|` symbol) between them? That tells Google you want **both** fonts. 

13. Navigate to the [Google Fonts page](https://www.google.com/fonts) again to grab the exact name for your fonts (uppercase letters make a difference!) and paste them into line 5 appropriately.

14. Lines 8 and 14 specify which font to use for headers, and which font to use for body text. Change the lines appropriately.

15. Change my silly text for a paragraph that explains what the fonts are, and why they work for this purpose. Commit your changes.

16. Go to the ```github.io``` version of your repository (if you forget the address, you can find it under the 'Settings' tab on your normal repository page when you're in the gh-pages branch). 

17. Reload the page several times to clear the older version you've already looked at and to replace it with your version. Ta da! Not only have you thought carefully about typography and fonts, you've also learned how to serve a webpage from a GitHub repository.

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/3O9gBpxh23A?rel=0" title="Updating your web page's fonts" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

**Hint:** For basic HTML, [W3schools has a really good guide to keep around](http://www.w3schools.com/html/default.asp).

### Going further with GitHub Pages

Now that you have learned the basics of creating a simple website using GitHub, you have the ability to go further. Using the DH Box, you can build a simple website through GitHub Pages using the MkDocs static site generator. Navigate to the [static site generator exercise using GitHub Pages in the supporting materials](../supporting materials/gh-pages.md).

-----

## Colour

There's a lot of bumpf out there on the 'pyschology of colour'. Google it to see what I mean ([Youth Designer has a good example](http://www.youthedesigner.com/graphic-design-resources/infographic-graphic-design-resources/infographic-a-color-guide-for-designers/)). A lot of what you see here isn't so much psychology as it is associations (and indeed, western associations, at that). Associations are important of course; you don't want to undermine your message by making some unfortunate connections.

If you decided to communicate findings via a website, below are some hints/tips for the proper use of colour: 

> 1. One where the colours **support** the broader message of the page.
> 2. And the other where the colours **undermine** that broader message. 

1. Explain, in both cases, how your colour choices enhance and/or detract.
2. Alternatively, you can make a one page slide in PowerPoint doing the same thing.

<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/ubiGLkh0aoY?rel=0" title="Web design using colours" frameborder="0" gesture="media" allowfullscreen></iframe>
<br>

### Resources

Below is a graphic and a video tutorial from Lynda.com (requires sign-up for free trial) to help with the theoretical side of things:

![Image showing color theory graphic](http://paper-leaf.com/wp-content/uploads/2010/01/ct_1920.jpg)

Visit the tutorial [Understanding the rules of color, Lynda.com (requires sign-up for free trial)](https://www.lynda.com/Graphic-Design-tutorials/Understanding-rules-color/419419/534020-4.html)

To learn how to style your webpage appropriately, you can [follow this tutorial on CSS from codeacademy.com](https://www.codecademy.com/learn/learn-css).

Below is a graphic that presents how colours are perceived in different cultures:

![Image showing colours in other cultures](http://infobeautiful3.s3.amazonaws.com/2013/01/1276_colours_in_culture.png)

-----

## Creating an online exhibit with Omeka

[Omeka](https://omeka.org/) is an open source Content Management System (CMS) for sharing digital collections and creating media-rich online exhibits. A CMS is a web program that manages web content including graphics, text, videos, and more. A CMS allows users to upload their content via a Graphical User Interface (GUI) and organizes it into appropriate folder structures. Traditional websites are programmed from the ground up &mdash; everything from structure, to styling, to creating folders and specifiying where multi-media content is located. 

The main advantage of using a CMS is that it requires little to no actual background-level programming. That being said, anyone can edit a CMS's source code files, add their own, or modify them to fit their needs. Most CMSs are built with [PHP](https://en.wikipedia.org/wiki/PHP), a web scripting language used to dynamically create content. However, most CMSs are also accompanied by massive native and third party plugin libraries that allow users to modify their website without touching any source code. Examples of CMSs include Wordpress, Drupal, Grav, Known, Joomla, and many more. 

Unlike many popular CMSs, Omeka is not a blogging platform. Omeka is used to create online exhibits. Today we are going to create a simple online exhibit. 

Our overall steps are as follows:

1. Create a subdomain of your website where Omeka will live. This will allow you to host Omeka as an entity of its own on your website, keeping your main website separate.
2. Install Omeka through cPanel on Reclaim Hosting.
3. Create an online exhibit with several historical items.
4. Change the style of our Omeka site by modifying the CSS of our theme.  

### Creating a subdomain

1. Login to your Reclaim Hosting account through the [Reclaim Hosting login page](http://portal.reclaimhosting.com/).

2. In the client area, select the cPanel tab.

    ![Image showing cPanel](/images/fig1.png)

3. Under the Domains section, select Subdomains. Typically, a subdomain divides your overall website into distinct portions. For instance, you could have your landing page at `mysite.com`, your blog at `blog.mysite.com`, and your class work at `hist3814.mysite.com`. That way each subdomain could have different styles and serve different purposes, but still be connected to your overall domain. You can add as many subdomains to your site as you'd like. 

    Subdomains are essentially just an easier way of organizing your files and showing distinct differences from your main domain. You could technically also do `mysite.com/blog` or `mysite.com/hist3814`. In that case, however, it seems expected they would all be styled similarly to `mysite.com`. Furthermore, it might cause file structure issues to have, for example, Wordpress running your `mysite.com` and Omeka running `mysite.com/Omeka`. It's best to stick with your free subdomains.

    ![Image showing Subdomains section of cPanel](/images/fig2.png)

4. Enter the name of your online exhibit in the Subdomain field. You could simply put `omeka`, `omeka-test`, etc. or get more descriptive and say `gatineau-fire-maps`. Choose a title relevant to your Omeka site's purpose.

5. Leave the Domain field set to your domain.

6. The Document Root will be automatically created (an advantage of adding a subdomain!). I would not recommend changing this, but if you want to further organize your folder structure, you are able to change the location.

    ![Image showing how to create a subdomain in cPanel](/images/fig3.png)

7. Click the Create button. It will take a moment, but your new subdomain will be approved. 

    ![Image showing successful subdomain creation in cPanel](/images/fig4.png)

**NB Since the subdomain has nothing in it, if you navigate to it now, you will see 'Index of/' showing the file structure. This is normal.**

### Installing Omeka 

1. Navigate back to your cPanel home page. 

2. Under the Applications section, select Omeka. 

    ![Image showing web applications available to install in cPanel](/images/fig5.png)

3. On the right side, click the '+ install this application' button. 

    ![Image showing the Omeka application in cPanel](/images/fig6.png)

4. Under the Location section, select the subdomain you created in the previous instructions. Do not choose your main `mysite.com` domain. Choose your `omeka.mysite.com` domain or your variant of it. You can choose the `https` or `http` version. Note, however, that `https` is more secure.

5. Delete `cms` under Directory (Optional). We want Omeka installed to the root of our subdomain, not in a folder called `cms`. If you were installing Omeka to your main site, then you'd want a subdirectory called `cms`.

    ![Image showing how to set up Omeka domain](/images/fig7.png)

6. Under the Version section, leave the settings as they are. Make sure 'I accept the license agreement' is selected. It's also good practice to allow it to update as needed and to allow backups.

7. Under the Settings section, either create a new Administrator Username and Administrator Password or securely record the Administrator Username and Administrator Password generated for you. (You can click Show Password to show it.) **REMEMBER YOUR LOGIN INFORMATION! You NEED the username and password to make changes to your Omeka site.**

8. Add an Administrator Email.

9. Change the Website Title to a fitting and appropriate title.

    ![Image showing Omeka login and admin information](/images/fig8.png)

10. Under Advanced, leave the default settings.

11. Click the Install button. You will be redirected to 'My Applications'. The installation may take a minute to process.

    ![Image showing where to access Omeka appication in cPanel](/images/fig9.png)

12. Select the middle link of your new Omeka application that says `omeka.mysite.com/admin` or your variant of the subdomain.

    ![Image showing how to access Omeka admin in cPanel](/images/fig10.png)

13. Login using your Administrator Username and your Administrator Password.

    ![Image showing how to log in to Omeka admin](/images/fig11.png)

14. At the top of the admin page, click on Settings.

15. Scroll down to the bottom. In the ImageMagick Directory Path field, type `/usr/bin`. Reclaim Hosting comes with ImageMagick preinstalled. ImageMagick resizes and generates thumbnails of your images.

    ![Image showing ImageMagick file path](/images/fig12.png)

16. Click Save Changes.

### Uploading content to Omeka

For the purposes of this option, we will use the [Gatineau Valley Historical Society fire insurance maps](http://www.gvhs.ca/research/maps/maps-fire-insurance.html) used in [Module 4, Exercise 8](#exercise-8-simple-mapping-and-georectifying). You are also allowed to use any historical sources to create an exhibit. Maybe you want to choose historical newspapers that have been digitized from the Library and Archives or the war diary from [Module 2, Exercise 2](../module-2/Exercises/#exercise-2-wget). Just make sure to note where you got your sources and, preferably, that you can download them as images.

1. On the left side, select Collections.

    ![Image showing Collections panel in Omeka](/images/fig13.png)

2. Click Add a Collection. 

    ![Image showing how to Add Collection in Omeka](/images/fig14.png)

3. My new collection will be fire insurance maps. Under Title, add Maps of the Gatineau Valley Fire Insurance Plans. 

4. Go through each metadata field and fill in as much information as you can about your collection.

5. Under Add Collection, click Public to make your collection publicly viewable. Click Add Collection.

    ![Image showing how to fill out collections details in Omeka](/images/fig15.png)

6. On the left side, select Items.

7. Click Add an item.

    ![Image showing how to add an Item in Omeka](/images/fig16.png)

8. Navigate to the [Gatineau Valley Historical Society Fire insurance maps](http://www.gvhs.ca/research/maps/maps-fire-insurance.html) or your own source of historical files.

9. Using the information provided with first map, fill in as much information as you can about your item. 

10. Click on the map image.

11. Right click and save the image somewhere handy like your desktop. 

12. Select the Files tab.

    ![Image showing how to upload file to an Item in Omeka](/images/fig18.png)

13. Click Browse and choose your image file (note you cannot upload a single image larger than 128MB).

14. On the right side under Collection, select your Collection and make sure it is set to Public.

    ![Image showing how to add the Item in Omeka](/images/fig17.png)

15. Click Add Item. It may take a few minutes to upload.

    ![Image showing successful upload of Item in Omeka](/images/fig19.png)

16. On the right side, click the middle, blue View Public Page button.

    ![Image showing Item page in Omeka](/images/fig21.png)

17. Go ahead and upload several exhibit items. If you can find other items related to your collection elsewhere, that'd be great too. 

18. Go to your variant of the `omeka.mysite.com` subdomain to view how the page looks to the public.

### Styling our exhibit (and making it more accessible!)

1. At the top of the admin page, click Appearance. The default theme is 'Thanks, Roy'. You can choose any theme you want. They are all different and each has different advantages and disadvantages for editing.

2. For this option, we will use the 'Thanks, Roy' theme. 

    **NB If you choose a different theme to modify, you may see different options. Proceed at your own intent.**

3. Click the blue Configure Theme button. Each theme configuration allows you to change basic style and content settings.

    ![Image showing how to configure default theme in Omeka](/images/fig22.png)

4. With the configuration page open in one tab, open your `omeka.mysite.com` to view the public page. Whenever you make an update, simply refresh the public page to view it.

5. Notice the Browse Items and Browse Collections links on the left of your public page are a bit light and hard to read. In the configuration, copy the text colour hex code `#444444`.

6. Navigate to the [Color Hex website](http://www.color-hex.com/) and search `#444444`. Hex codes are an internet convention where a series of numbers or numbers and letters correspond with a unique colour. 

7. Scroll down to Shades of `#444444`. I think `#1b1b1b` looks dark enough for a solid contrast.

8. Navigate back to the Omeka configuration page and replace the Text and Links fields hex codes of `#444444` with `#1b1b1b`.

    ![Image showing how to replace colour codes in default theme configuration in Omeka](/images/fig23.png)

9. On the right side, click Save Changes.

10. Refresh the public page and notice the text darkens. This will help make your website more readable.

#### Using the browser inspector to make design easier

1. Navigate to your public Omeka page.

2. Right click on the "Featured Item" text.

3. Select Inspect Element. The browser inspection tool allows you to view the code behind a website. 

    **NB Chrome and Firefox have great inspector tools. Not all browsers have these tools, however, notably Safari.**

    ![Image showing how to access inspector tool in Firefox browser](/images/fig24.png)

4. The font is not that easy to read either. We will change it, but first let's find the current font. Scroll down on the right side under the Rules tab until you see the body CSS. This rule shows the font is called PT serif, written like the following:

        body {
            font-family: "PT Serif", Times, serif;
        }

    ![Image showing inspector tool to access element style](/images/fig25.png)

5. Go to [Google Fonts](https://fonts.google.com/) to choose a new, more readable font.

6. Search Roboto. Roboto is a clean, easy to read font.

7. Click the red plus sign to select the font. It will add to a queue below.

8. Click the black queue bar.

9. Scroll to where it says Specify in CSS. 

10. Copy the text that says `font-family: 'Roboto', sans-serif;`. We will add this rule to our CSS file.

    ![Image showing Roboto font style rule in Google Fonts](/images/fig26.png)

11. Navigate to your cPanel home page and select File Manager at the top of the page.

    ![Image showing where to access File Manager in cPanel](/images/fig27.png)

12. On the left side click on the folder for your Omeka site. The folder should have the same name as your domain. For instance, if your site is called `omeka.mysite.com`, the folder will be called `omeka.mysite.com` unless you changed the name earlier.

13. Double click each folder until you are in the `css` folder: Themes >> Default >> css

14. Right click `style.css` and select Edit. Reclaim Hosting has some great editing tools within the cPanel so you don't have to make updates within your desktop text editor and then reupload the files.

    ![Image showing how to edit style css file](/images/fig28.png)

15. Search `font-family` by hitting ctrl-f (Windows) or cmnd-f (Mac). We **ONLY** want to change the rules that say `font-family: "PT Serif", Times, serif;`.

    ![Image showing default font rule in style css file](/images/fig29.png)

16. Use the search to replace each instance of `font-family: "PT Serif", Times, serif;` with `font-family: 'Roboto', sans-serif;`.

    ![Image showing updated Roboto font in style css file](/images/fig30.png)

17. Click the blue Save Changes button at the top right of the editor.

18. Navigate to your Omeka site and refresh the page. Notice the font changes from PT Serif to Roboto.

    **Before (default PT Serif font)**
    ![Image showing Omeka public page before font change](/images/fig31.png)

    **After (updated Roboto font)**
    ![Image showing Omeka public page after font change](/images/fig32.png)

19. Use your browser's inspector to find out the style rules of any specific element on a web page. 

20. If you make any major mistakes and want to start from scratch, you can copy the original `style.css` [file from GitHub](https://raw.githubusercontent.com/omeka/theme-thanksroy/master/css/style.css), paste it into your file, and save the changes. This will revert it back to the original style.

**NB** It is important to note that for our purposes, we edited the default `style.css` file directly. This was to introduce you to CSS and making changes to the source code. Typically, you'd want to add a new file called, for example, `custom.css` and specify the path to that file in our source code. That way you keep your own changes distinct from the default source code files. However, that would involve editing different PHP rules which is beyond the scope of this option. This is very important for making upgrades. If your theme ever upgrades, you will lose all your changes if you only edited the default `style.css`. This applies to any file type. Therefore, you may want to keep a copy of your changes somewhere handy, like on your desktop.

-----

## More Resources

Below are more resources, tutorials, and things to explore.

### Accessibility and Design
While most of this applies to websites, think also about how the general principles apply to other ways and means of telling our data stories.

+ [How People with Disabilities Use the Web](http://www.w3.org/WAI/intro/people-use-web/)
+ [Web Content Accessibility and Mobile Web](http://www.w3.org/WAI/mobile/overlap.html)
+ [Accessibility in HTML5](http://www.clarissapeterson.com/2012/11/html5-accessibility/)
+ [Web Accessibility Evaluation Tool](http://wave.webaim.org/)
+ [Considering the User Perspective](http://webaim.org/articles/userperspective/)
+ [Constructing a POUR Website](http://webaim.org/articles/userperspective/) Percievable, Operable, Understandable, Robust. Applies much wider than design of websites.
+ [Checking Microsoft Office-generated documents for accessibility](https://support.office.com/en-us/article/Check-for-accessibility-issues-a16f6de0-2f39-4a2b-8bd8-5ad801426c7f?CorrelationId=19c77f4b-7307-4697-9320-8bbbe05aa85a&ui=en-US&rs=en-US&ad=US)

### Infographics and Storytelling
#### Infographics

+ [The Difference between Infographics and Visualizations](https://eagereyes.org/blog/2010/the-difference-between-infographics-and-visualization)
+ [Design hints for infographics](https://piktochart.com/blog/infographics-design-series-design-your-infographic-like-a-pro/)
+ [Piktochart](http://piktochart.com/)
+ [Infogr.am](https://infogr.am/)
+ [Easel.ly](http://www.easel.ly/)

#### Storytelling

+ [Creatavist](https://creatavist.com/)
+ [Medium](https://medium.com/)
+ [Cowbird](http://cowbird.com/)
+ [Exposure](https://exposure.co/)
+ [Timeline.js](https://timeline.knightlab.com)
+ [Storymap](https://storymap.knightlab.com/)

### ManyLines

[ManyLines](http://tools.medialab.sciences-po.fr/manylines) is an application that allows you to create narratives from network graphs. In essence, you upload a network file in `.gexf` format (which you can export from Gephi) and it renders it on the screen. There are some layout options to make the graph more intelligible. Then, you take a series of snapshots zoomed in on the graph in different places, and add text to describe what it is that's important about these networks. The app puts a Prezi-like wrapper around your snapshots, and the whole can then be embedded in a website or be used as a standalone website. [Check out my first attempt on medialab.](http://tools.medialab.sciences-po.fr/manylines/embed#/narrative/051b0a7a-c1af-458f-b6a1-e3b0964e577f) 

You can also embed nearly anything in the narrative panels &mdash; Youtube videos, [timeline.js](http://timeline.knightlab.com/) &mdash; as long as you know how to correctly format an [iframe](http://www.w3schools.com/tags/tag_iframe.asp).  

To give this a try, why not use the Texan Correspondence network we generated in earlier modules? Export it in `.gexf` format from Gephi, import to ManyLines, and go! The interface is fairly straightforward. Just follow the prompts.

**Caveat Utilitor** I don't know how long anything made with ManyLines will live on their website. But, knowing what you know about wget and other tools, do you see how you could archive a copy on your own machine? ManyLines is available on [GitHub](https://github.com/medialab/manylines) so you can certainly use it locally.

### Leaflet

Maps can be created through a variety of services ([TileMill](https://tilemill-project.github.io/tilemill/), [Carto](https://carto.com/) and [mapbox](http://mapbox.com) for instance). These can then be embedded in your webpages or documents. Often, that's enough. But sometimes, you'd like to take control, and keep all the data, all the map, under your own name, in your own webspace. Visit the gentle introduction to using [leaflet.js in our supporting materials](../supporting materials/leaflet.txt.md) to make, style, and serve your maps. Also visit [a template on my GitHub repository](https://github.com/shawngraham/daea) for mapping with leaflet, drawing all of your point data and ancillary information from a CSV file. Leaflet also has [a list of background maps you can use](http://leaflet-extras.github.io/leaflet-providers/preview/index.html).

#### Leaflet in the field: Pembroke Soundscapes Project

Visit the [Pembroke Soundscapes Project](http://pembrokesoundscapes.ca/map) for an example of an academic historical project using Leaflet. This project uses an interactive map with sound clips to explore the industrial history of Pembroke, Ontario. 

### Designing Maps with Processing and Illustrator

Nicolas Felton is a renowned designer. Watch [his 90 minute workshop on Skillshare](http://www.skillshare.com/classes/design/Data-Visualization-Designing-Maps-with-Processing-and-Illustrator/1063775924).

**NB I do not use Processing or Illustrator, but Processing is free and Inkscape can do many of the things that Illustrator does.**
