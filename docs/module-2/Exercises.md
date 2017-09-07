# Module 2 Exercises

_All five exercises are on this page. Don't forget to scroll. If you have difficulties, or if the instructions need clarification, please click the 'issues' button and leave a note. Feel free to fork and improve these instructions, if you are so inclined. Remember, these exercises get progressively more difficult, and will require you to either download materials or read materials on other websites. Give yourself plenty of time. Try them all, and remember you can turn to your classmates for help. Work together!_

*DO NOT suffer in silence as you try these exercises! Annotate, ask for help, set up an appointment, or find me in person.*

# Background
Where do we go to find data? Part of that problem is solved by knowing what question you are asking, and what _kinds_ of data would help solve that question. Let's assume that you have a pretty good question you want an answer to - say, something concerning social and household history in early Ottawa, like what was the role of 'corner' stores (if such things exist?) in fostering a sense of neighbourhood - and begin thinking about how you'd find data to explore that question.

The exercises in this module cover:

+ The Dream Case
+ Wget
+ Writing a program to extract data from a webpage
+ Collecting data from Twitter

There is so much data available; with these methods, we can gather enormous amounts that will let us see large-scale macroscopic patterns. At the same time, it allows us to dive into the details with comparative ease. The thing is, not all digital data are created equally. Google has spent millions digitizing *everything*; newspapers have digitized their own collections. Genealogists and local historical societies upload yoinks of digitized photographs, wills, local tax records, [you-name-it](http://www.bytown.net/), *every day*. But, consider what Milligan has to say about ['illusionary order'](http://ianmilligan.ca/2012/03/26/illusionary-order-cautionary-notes-for-online-newspapers/):

> [...] poor and misunderstood use of online newspapers can skew historical research. In a conference presentation or a lecture, it’s not uknown to see the familiar yellow highlighting of found searchwords on projected images: indicative of how the original primary material was obtained. But this historical approach generally usually remains unspoken, without a critical methodological reflection. As I hope I’ll show here, using Pages of the Past uncritically for historical research is akin to using a volume of the Canadian Historical Review with 10% or so of the pages ripped out. Historians, journalists, policy researchers, genealogists, and amateur researchers need to at least have a basic understanding of what goes on behind the black box.

Ask yourself: what are some of the key dangers? Reflect: how have you used digitized resources uncritically in the past? Remember: 'To digitize' doesn't - or shouldn't - mean uploading a photograph of a document. There's a lot more going on that that. We'll get to that in a moment.

# EXERCISE 1: The Dream Case
In the dream case, your data are not just images, but are actually sorted and structured into some kind of pre-existing database. There are choices made in the *creation* of the database, but a good database, a good project, will lay out for you their decision making, their corpora, and how they've dealt with ambiguity and so on. You search using a robust interface, and you get a well-formed spreadsheet of data in return. Two examples of 'dream case' data:

+ [Epigraphic Database Heidelberg](http://edh-www.adw.uni-heidelberg.de/inschrift/suche)
+ [Commwealth War Graves Commission, Find War Dead](http://www.cwgc.org/find-war-dead.aspx)

Explore both databases. Perform a search of interest to you. In the case of the epigraphic database, if you've done any Latin, try searching for terms related to occupations; or you could search '[Figlin*](http://www.latin-dictionary.org/Latin-English-Dictionary/figlina)'. In the CWGC database, search your own surname. Download your results. You now have data that you can explore! Using the nano text editor in your DHBox, make a record (or records) of what you searched, the URL for your search & its results, and where you're keeping your data. Lodge a copy of this record in your repository.

# EXERCISE 2: Wget

You've already encountered wget in the introduction to this workbook, when you were setting up your DHBox to use Pandoc. In this exercise, I want you to do [Ian Milligan's wget tutorial at the Programming Historian](http://programminghistorian.org/lessons/automated-downloading-with-wget) to learn more about the power of this command, and how to wield that power properly. Skip ahead to step 2, since your DHBox already has wget installed. (If you want to continue to use wget after this course is over, you will have to install it on your own machine, obviously).

Once you've completed Milligan's tutorial, remember to put your history into a new markdown file, and to lodge a copy of it in your repository.

Now that you're _au fait_ with wget, I want you to use wget to download the Shawville Equity from the Quebec provincial archives in a responsible and respectful manner. Otherwise, you will look like a bot attacking their site. The data is in this location: `http://collections.banq.qc.ca:8008/jrn03/equity/src/`. Make a new directory: `$ mkdir equity` and then cd into it: `$ cd equity`. Make sure you're in the directory by typing `$ pwd`. Work out the command to download say ten years' worth only of the Equity OCR'd transcriptions (the .txt files); configure your command to retrieve only the txt files, as the pdfs are large and will take much time and bandwidth to acquire. (Ok, I'm not heartless - scroll to the bottom of this page to see what the command should be).

Add your command to your history file, and lodge it in your repository.

Open some of the text files in Nano. How good, how careful was the 'object character recognition'? Part of the point of working with the Equity files is to show that even with horrible 'digitization', we can still extract useful insights. Digitization is more than simply throwing automatically generated files online. Good digitization requires scholarly work and effort! We will learn how to do this properly in the next exercise.

# EXERCISE 3: TEI

Digitization requires human intervention. This can be as straightforward as correcting errors or adjusting the scanner settings when we do OCR, or it can be the rather more involved work of adding a layer of semantic information to the text. When we mark up a text with the semantic hooks and signs that explain we are talking about 'London, Ontario' rather than 'London, UK', we've made the text a whole lot more useful for other scholars or tools. In this exercise, you will do some basic marking up of a text using standards from the [Text Encoding Initiative](http://www.tei-c.org/index.xml). (Some of the earliest digital history work was along these lines). The TEI exercise requires carefully attention to detail. Read through it before you try it. In this exercise, you'll transcribe a page from an abolitionist's pamphlet. You'll also think about ways of transforming the resulting XML into other formats. Make notes in a file to upload to your repository, and upload your XML and your XSL file to your own repository as well. (As an added optional challenge, create a gh-pages branch and figure out the direct URL to your XML file, and email that URL to me).

The exercise may be found [in our supporting materials](../supporting materials/tei.md).

I will note that a perfectly fine final project for HIST3814 might be to use this exercise as a model to markup a single issue of the Equity and suggest ways this material might be explored. Remember to make (and lodge in your repository) a file detailing the work you've done and any issues you've run into.

# EXERCISE 4: APIs

Sometimes, a website will have what is called an 'application programming interface'. In essence, this lets a program on your computer talk to the computer serving the website you're interested in, such that the website gives you the data that you're looking for.

That is, instead of *you* punching in the search terms, and copying and pasting the results, you get the computer to do it. More or less. The thing is, the results come back to you in a machine-readable format - often, JSON, which is a kind of text format. It looks like this:
![Image showing JSON formating](http://i.imgur.com/LtZWyle.png)

The 'Canadiana Discovery Portal' has tonnes of materials related to Canada's history, from a wide variety of sources. Its search page is at: http://search.canadiana.ca/

+ Go there, and search "ottawa" and set the date range to 1800 to 1900. Hit enter. You are presented with a page of results -56 249 results! That's a lot of data. But do you notice the address bar of your browser? It'll say something like this:

http://search.canadiana.ca/search?q=ottawa&field=&df=1900&dt=1900

Your search query has been put into the URL. You're looking at the API! Everything after /search is a command that you are sending to the Canadiana server.

Scroll through the results, and you'll see a number just before the ?

http://search.canadiana.ca/search/2?df=1800&dt=1900&q=ottawa&field=

http://search.canadiana.ca/search/3?df=1800&dt=1900&q=ottawa&field=

http://search.canadiana.ca/search/4?df=1800&dt=1900&q=ottawa&field=

....all the way up to 5625 (ie, 10 results per page, so 56249 / 10).

If you go to http://search.canadiana.ca/support/api you can see the full list of options. What we are particularly interested in now is the bit that looks like this:

`&fmt=json`

Add that to your query URL. How different the results now look! What's nice here is that the data is formatted in a way that makes sense to a machine - which we'll learn more about in due course.

If you look back at the full list of API options, you'll see at the bottom that one of the options is 'retrieving individual item records'; the key for that is a field called 'oocihm'. If you look at your page of json results, and scroll through them, you'll see that each individual record has its own oocihm number. If we could get a list of those, we'd be able to programmatically slot them into the commands for retrieving individual item records:

http://search.canadiana.ca/view/oocihm.16278/?r=0&s=1&fmt=json&api_text=1

The problem is: how to retrieve those oocihm numbers. The answer is, 'we write a program'. And the program that you want can be [found on Ian Milligan's website](http://ianmilligan.ca/api-example-sh/). Study that program carefully. There are a number of useful things happening in there, notably 'curl', 'jq', 'sed', 'awk'. curl  is a program for downloading webpages, jq for dealing with json, and sed and awk for searching within and cleaning up text. If this all sounds greek to you, there is an excellent gentle introduction over at [William Turkel's blog](http://williamjturkel.net/2013/06/15/basic-text-analysis-with-command-line-tools-in-linux/).

So here's what we're going to do.

1. We need jq. We install it into our DHBox with `$ sudo apt-get install jq -y`
2. We need to create a program. Make a new directory for this exercise like so: `$ mkdir m2e4`. Then, change into that directory by typing `$ cd m2e4`. Make sure that's where you are by typing `$ pwd`. Now, make an empty file for our program with `$ touch canadiana.sh`. Touch makes an empty file; the .sh in the filename indicates that this is a shell script.
3. Open the empty file with `$ nano canadiana.sh`. Now, the program that Ian Milligan wrote makes calls to the API that *used to live* at eco.canadiana.ca. But note the [error message on Canadiana's website](http://eco.canadiana.ca/view/oocihm.16278/?r=0&s=1&fmt=json&api_text=1). So we have to change Milligan's script so that it points to the API at search.canadiana.ca. Copy the script below into your empty canadiana.sh. If you want, adjust the search parameters (in the line starting with `pages`) for material you're more interested in.

```bash
#! /bin/bash

pages=$(curl 'http://search.canadiana.ca/search?q=ottawa*&field=&so=score&df=1914&dt=1918&fmt=json' | jq '.pages')

# this goes into the results and reads the value of 'pages' in each one of them.
# it then tells us how many pages we're going to have.

echo "Pages:"$pages

# this says 'for each one of these pages, download the 'key' value on each page'

for i in $(seq 1 $pages)
do
        curl 'http://search.canadiana.ca/search/'${i}'?q=montenegr*&field=&so=score&df=1914&dt=1918&fmt=json' | jq '.docs[] | {key}' >> results.txt
done

# the next two lines take the results.txt file that is quite messy and clean it up. I'll try to explain what they all mean. Basically, tr deletes a given character - so we delete quotation marks "\"" (the slash tells the computer not to treat the quotation mark as a computer code, but as a quotation mark itself), to erase spaces, and to find the phrase "key:" and delete it too.

sed -e 's/\"key\": \"//g' results.txt | tr -d "\"" | tr -d "{" | tr -d "}" | tr -s " " | sed '/^\s*$/d' | tr -d ' ' > cleanlist.txt
# this adds a prefix and a suffix.

awk '$0="search.canadiana.ca/view/"$0' cleanlist.txt| awk '{print $0 "/1?r=0&s=1&fmt=json&api_text=1"}' > urlstograb.txt

# then if we want we can take those URLs and output them all to a big text file for analysis.

wget -i urlstograb.txt -O output.txt
```
Hit ctrl+x to exit Nano, and save the changes.

Before we can run this program, we have to tell DHBox that it is alright to run it. We do that by changing the 'permissions' on the file, like so:

`$ chmod 755 canadiana.sh`

And now we can run the program:

`$ ./canadiana.sh`

Ta da! You now have a pretty powerful tool now for grabbing data from one of the largest portals for Canadian history! Download your output.txt file to your computer via the file manager and have a look at it. Make sure to make a file noting what you've done, commands you've made, etc, and lodge it in your repository.

# EXERCISE 5: Mining Twitter

Ed Summers is part of a project called '[Documenting the Now](http://www.docnow.io/)' which is developing tools to collect and understand the historical materials being shared (and lost) on social media. One component of Documenting the Now is the Twitter Archiving Tool, '[Twarc](https://github.com/DocNow/twarc)'. In this exercise, you are going to use Twarc to create an archive of Tweets relevant to a current trending news topic.

1. First of all, you need to set up a Twitter account, if you haven't already got one. Do so, but make sure to minimize any personal information that is exposed. For instance, don't make your handle the same as your real name. Turn off geolocation. Do not give your actual location in the profile. View the settings, and make sure all of the privacy settings are dialed down. For the time being, you *do* have to associate a cell phone number with your account. You can delete that once you've done the next step.
2. Go to [https://apps.twitter.com/](https://apps.twitter.com/) and click on ‘new app’. Then, on the ‘new application’ page, just give your app a name like my-twarc’ or similar, and website use the Crafting Digital History site url (although for our purposes any website will do). You don’t need to fill in any of the rest of the fields. Continue on to the next page (tick off the box saying you’ve read the developer code of behaviour). This next page shows you all the details about your new application.
3. Click on the ‘keys and access tokens’ tab. Copy the consumer key, the consumer secret to a text file. Click on the ‘create access tokens’ at the bottom of the page. This generates an access token and an access secret. Copy those to your text file, save it. **do not put this file in your repo or leave it online anywhere** ![Image showing Twitter access tokens](http://i.imgur.com/mM4hZNN.png)
4. In your DHbox, at the command line, type `$ pip install twarc`. Twarc is written in python, which is already installed in DHbox. 'Pip' is a package manager for installing new python modules and packages. If you forget the `sudo`, you will get an error to the effect that you don't have permission. So sudo!
5.  Now type `$ twarc configure ` and give it the information it asks for (your consumer secret etc).
6. You're now ready to search. For instance, `$ twarc search canada150 > search.json` will search Twitter for posts using the canada150 hashtag. *Wait! Don't run that command!* If you search for that, there are, what, 36 million Canadians? How many tweets is that likely to be? Quite a lot - and the command will run quietly for days grabbing that information, writing it to file, and you'll be sitting looking at the screen wondering if anything is happening. Try something smaller, more contained for now, `$ twarc search hist3814o > search.json`.  Note that Twitter only gives access to the last two weeks or so via search. For grabbing the stream _as an event happens_ you'd use the `twarc stream` command - see the Twarc documentation for more.
7. It might take some time for the search to happen. You can always force-stop the search by hitting ctrl+c. If you do that though there could be an error in the formatting of the file which will throw an error when you get to step 10. You can still open the json in a text editor though, but you will have to go to the end of the file and fix the formatting.
8. The data being collected is in json format. That is, a list of 'keys' and 'values'. This is a handy format for computers, and some data visualization platforms require data in this format. For our purposes we might want to transform the json into a csv (comma separated) table - a spreadsheet.
9. We will install a command that can convert the json to csv format like so: `$ sudo npm install json2csv --save -g`. Full details about the command can be found on [json2csv's Github repository](https://github.com/zemirco/json2csv#command-line-interface).
10. Convert your `search.json` to csv like so: `json2csv -i search.json -o out.csv`
11. Examine your data either in a text editor or in a spreadsheet. Use twarc to create a file with a list of ids. Lodge this list and your history and notes in your repository.

NB. Twitter forbids the sharing of the full metadata of a collection of tweets. You may however share a list of tweet IDs. See the Twarc documentation for the instructions on how to do that.

What can you do with this data? Examine the Twarc repository, especially its utilities. You could extract the geolocated ones and map them. You could examine the difference between 'male' and 'female' tweeters (and how problematic might that be?). In your csv, save the text of the posts to a new file and upload it to something like [Voyant](http://voyant-tools.org) to visualize trends over time. Google for analyzes of twitter data to get some ideas.


# EXERCISE 6: Using Tesseract to turn a pdf into text

We've all used pdfs - in academia, we often use a pdf to make sure that a page of text looks like an actual physical page of paper. PDFs always look the same on whatever machine they are displayed on, because they contain within themselves the complete description of what the 'page' should look like. If you've ever selected text within a pdf, you were only able to do this because there was within the pdf a text layer on top of the image layer. But when we digitize old newspapers, the pdf that results only contains the image layer, not the text. To turn that image into text, we have to do what's called 'object character recognition', or OCR. An OCR algorithm looks at the pattern of pixels in the image, and maps these against the shapes it 'knows' to be an A, or an a, or a B, or a &, and so on. Cleaner, sharper printing gives better results as do hi resolution images free from noise. People who have a lot of material to OCR use some very powerful tools to identify blocks of text within the newspaper page, and then train the machine to identify these, a process beyond us just now (but visit [this tesseract q & a on stackoverflow](https://stackoverflow.com/questions/28591117/how-do-i-segment-a-document-using-tesseract-then-output-the-resulting-bounding-b#28640570) if you're interested).

In this exercise, you'll:

1. install the Tesseract OCR engine into your DHBox
2. download an edition of the Equity
3. install and use pdftk to burst the pdf into individual one-page files
4. install and use imagemagick to convert the pdf into tiff image format
5. use Tesseract to OCR the resulting pages.

Begin by making a new director for this exercise: `mkdir ocr-test`. Change directories into it: `cd ocr-test`

1. `$ sudo apt-get install tesseract-ocr` will grab the latest version of tesseract and install it into your dhbox. Enter your password when the computer asks for it.
2. `$ sudo apt-get install imagemagick` to install imagemagick
3. `$ sudo apt-get install pdftk` to install pdftk.
4. Now let's grab an edition of the Equity. Use wget to grab the pdf from July 4th 1957.
5. Let's burst it into individual pages. The command is `pdtk <input file> burst`, so `$ pdftk 83471_1957-07-04.pdf burst`
6. Let's convert the first file to tiff with imagemagick's convert command: `$ convert -density 300 pg_0001.pdf -depth 8 -strip -background white -alpha off file.tiff` You want a high density image, which is what the -density and the -depth flags do; the rest of the command formats the image in a way that Tesseract expects to encounter text. This command might take a while. Just wait, be patient.
7. Extract text! `$ tesseract file.tiff output.txt` This might also take some time.

Download the output.txt file with the DHBox filemanager. Open the file with a text editor (there might be a lot of white space at the start of the file, fyi). Grab the txt file created by the Provincial Archives. Is yours better or worse than theirs? Look up the [Tesseract wiki](https://github.com/tesseract-ocr/tesseract/wiki/Command-Line-Usage). What other options could you use with the tesseract command to improve the results? For future reference, here are two guides to automating bulk OCR (multiple files) with tesseract: [Peirson's](https://diging.atlassian.net/wiki/display/DCH/Tutorial%3A+Text+Extraction+and+OCR+with+Tesseract+and+ImageMagick), [Schmidt's](http://benschmidt.org/dighist13/?page_id=129).













### wget command to grab The Equity

Hey - you've scrolled all the way down here. Here's the wget command to nicely download the Equity txt files _but don't run it just yet_:
`wget http://collections.banq.qc.ca:8008/jrn03/equity/src/ -A .txt -r --no-parent -nd –w 2 --limit-rate=20k`

When you run this command, it will go through the entire file structure a couple of times, 'rejecting' index.html etc because we've asked it to just grab the .txt files. Be patient. How would you change it to grab just the pdfs?

Now, the reason I ask you to not run it just yet is because of memory. This is going to take a lot of memory up when it's done. If you have wget installed on your own machine, then you'll likely have no problem. _However_ our DHBox is being shared by many people, and the amount of memory available can become an issue. **So** what we're going to do is modify the command so that we only grab a subset of the files. Given that each filename contains within it the date of the issue, **download only the .txt files for a particular decade**. The command below is modified so that wget, as it searches through each subdirectory, only grabs the ones from the 1880s - do you see the crucial bit that does that?:  

`wget http://collections.banq.qc.ca:8008/jrn03/equity/src/ -A "*188*".txt -nc -r --no-parent -nd –w 2 --limit-rate=20k`

Alternatively, given that the folder structure is done by year and month a quicker route might be to just run the original wget command ten times, changing the folder each time:

'`wget http://collections.banq.qc.ca:8008/jrn03/equity/src/1883/ -A .txt -r --no-parent -nd –w 2 --limit-rate=20k`'

then

`wget http://collections.banq.qc.ca:8008/jrn03/equity/src/1884/ -A .txt -r --no-parent -nd –w 2 --limit-rate=20k`

etc, changing the year. There's no one right way to do things, digitally; there are many paths. The crucial thing is that you find a way that makes sense for your own workflow, and that doesn't make you a drain on someone else's resources.
