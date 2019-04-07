# Module 2 Exercises

All five exercises are on this page. Don't forget to scroll. If you have difficulties, or if the instructions need clarification, please click the 'issues' button and leave a note. Feel free to fork and improve these instructions, if you are so inclined. Remember, these exercises get progressively more difficult, and will require you to either download materials or read materials on other websites. Give yourself plenty of time. Try them all, and remember you can turn to your classmates for help. Work together!

**DO NOT suffer in silence as you try these exercises! Annotate, ask for help, set up an appointment, or find me in person.**

## Background
Where do we go to find data? Part of that problem is solved by knowing what question you are asking, and what **kinds** of data would help solve that question. Let's assume that you have a pretty good question you want an answer to &mdash; say, something concerning social and household history in early Ottawa, like what was the role of 'corner' stores (if such things exist?) in fostering a sense of neighbourhood &mdash; and begin thinking about how you'd find data to explore that question.

The exercises in this module cover:

+ The Dream Case
+ Wget
+ Writing a program to extract data from a webpage
+ Encoding transcribed text
+ Collecting data from Twitter
+ Coverting images to text with Tesseract 

There is so much data available; with these methods, we can gather enormous amounts that will let us see large-scale macroscopic patterns. At the same time, it allows us to dive into the details with comparative ease. The thing is, not all digital data are created equally. Google has spent millions digitizing **everything**; newspapers have digitized their own collections. Genealogists and local historical societies upload yoinks of digitized photographs, wills, local tax records, [you-name-it](http://www.bytown.net/), **every day**. But, consider what Milligan has to say about ['illusionary order'](http://ianmilligan.ca/2012/03/26/illusionary-order-cautionary-notes-for-online-newspapers/):

> [...] poor and misunderstood use of online newspapers can skew historical research. In a conference presentation or a lecture, it’s not uknown to see the familiar yellow highlighting of found searchwords on projected images: indicative of how the original primary material was obtained. But this historical approach generally usually remains unspoken, without a critical methodological reflection. As I hope I’ll show here, using Pages of the Past uncritically for historical research is akin to using a volume of the Canadian Historical Review with 10% or so of the pages ripped out. Historians, journalists, policy researchers, genealogists, and amateur researchers need to at least have a basic understanding of what goes on behind the black box.

Ask yourself: what are some of the key dangers? Reflect: how have you used digitized resources uncritically in the past? Remember: **To digitize** doesn't &mdash; or shouldn't &mdash; mean uploading a photograph of a document. There's a lot more going on than that. We'll get to that in a moment.

-----

## Exercise 1: The Dream Case
In the dream case, your data are not just images, but are actually sorted and structured into some kind of pre-existing database. There are choices made in the **creation** of the database, but a good database, a good project, will lay out for you their decision making, their corpora, and how they've dealt with ambiguity and so on. You search using a robust interface, and you get a well-formed spreadsheet of data in return. Two examples of 'dream case' data:
    
> + [Epigraphic Database Heidelberg](http://edh-www.adw.uni-heidelberg.de/inschrift/suche)
> + [Commwealth War Graves Commission, Find War Dead](https://www.cwgc.org/find/find-war-dead)

1. Explore both databases. Perform a search of interest to you. In the case of the epigraphic database, if you've done any Latin, try searching for terms related to occupations; or you could search [Figlina](http://www.latin-dictionary.org/Latin-English-Dictionary/figlina). 
2. In the CWGC database, search your own surname. Download your results. You now have data that you can explore! 
3. Using the Nano text editor in your DH Box, make a record (or records) of what you searched, the URL for your search and its results, and where you're keeping your data. 
4. Lodge a copy of this record in your repository.

-----

## Exercise 2: Wget

You've already encountered wget in the introduction to this workbook, when you were setting up your DH Box to use Pandoc. 

1. In this exercise, I want you to do [Ian Milligan's wget tutorial at the Programming Historian](http://programminghistorian.org/lessons/automated-downloading-with-wget) to learn more about the power of this command, and how to wield that power properly. Skip ahead to step 2, since your DH Box already has wget installed. (If you want to continue to use wget after this course is over, you will have to install it on your own machine, obviously.)

    Once you've completed Milligan's tutorial, remember to put your history into a new Markdown file, and to lodge a copy of it in your repository.

    Now that you're **au fait** with wget, we will do part of [Kellen Kurschinski's wget tutorial at the Programming Historian](https://programminghistorian.org/lessons/applied-archival-downloading-with-wget). I want you to use wget to download the Library and Archives Canada [14th Canadian General Hospital war diaries](http://collectionscanada.gc.ca/pam_archives/index.php?fuseaction=genitem.displayItem&lang=eng&rec_nbr=2005110&rec_nbr_list=3366167,3203123,2005097,2005100,2005101,2005099,2005096,2005110,2005108,2005106) in a responsible and respectful manner. Otherwise, you will look like a bot attacking their site.

    The URLs of this diary go from `http://data2.archives.ca/e/e061/e001518029.jpg` to `http://data2.archives.ca/e/e061/e001518109.jpg`. This is a total of 80 pages &mdash; note the last part of the URL goes from `e001518029` to `e001518109` for a total of 80 images.

2. Make a new directory: `$ mkdir war-diary` and then cd into it: `$ cd war-diary`. Make sure you're in the directory by typing `$ pwd`. 

    **NB Make sure you are in your parent directory `~`. To get there directly from any subdirectory, type `$ cd ~`. If you want to check your file structure quickly, go to the File Manager.**

    We will use a simple Python script to gather all the URLs of the diary images from the Library and Archives. Python is a general purpose programming language.

3. Type `$ nano urls.py` to open a new Python file called `urls`.

4. Paste the script below. This script grabs the URLs from `e001518029` to `e001518110` and puts them in a file called `urls.txt`: 

        urls = '';
        f=open('urls.txt','w')
        for x in range(8029, 8110):
            urls = 'http://data2.collectionscanada.ca/e/e061/e00151%d.jpg\n' % (x)
            f.write(urls)
        f.close

5. Hit ctrl+x, Y, enter to save and exit Nano.

6. Type `$ python urls.py` to run the Python script. 

7. Type `$ ls` and notice the `urls.txt` file.

8. Type `$ nano urls.txt` to examine the file. Exit Nano.

9. Type `$ wget -i urls.txt -r --no-parent -nd -w 2 --limit-rate=100k` to download all the URLs from the `urls.txt` file.

10. Type `$ ls` to verify the files were downloaded.

11. Add your command to your history file, and lodge it in your repository. For reference, visit [Module 1, Exercise 2](../module-1/Exercises/#exercise-2-getting-familiar-with-dh-box).

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/zK172_9QcL8?rel=0" title="Using wget to download historical sources" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

In [Exercise 6](#exercise-6-using-tesseract-to-turn-an-image-into-text), we will open some of the text files in Nano to judge the 'object character recognition'. Part of the point of working with these files is to show that even with horrible 'digitization', we can still extract useful insights. Digitization is more than simply throwing automatically generated files online. Good digitization requires scholarly work and effort! We will learn how to do this properly in the next exercise.

There's no one right way to do things, digitally. There are many paths. The crucial thing is that you find a way that makes sense for your own workflow, and that doesn't make you a drain on someone else's resources.

-----

## Exercise 3: TEI

Digitization requires human intervention. This can be as straightforward as correcting errors or adjusting the scanner settings when we do OCR, or it can be the rather more involved work of adding a layer of semantic information to the text. When we mark up a text with the semantic hooks and signs that explain we are talking about **London, Ontario** rather than **London, UK**, we've made the text a whole lot more useful for other scholars or tools. In this exercise, you will do some basic marking up of a text using standards from the [Text Encoding Initiative](https://tei-c.org/). (Some of the earliest digital history work was along these lines). 

The TEI exercise requires careful attention to detail. Read through it before you try it. In this exercise, you'll transcribe a page from an abolitionist's pamphlet. You'll also think about ways of transforming the resulting XML into other formats. Make notes in a file to upload to your repository, and upload your XML and your XSL file to your own repository as well. (As an added optional challenge, create a gh-pages branch and figure out the direct URL to your XML file, and email that URL to me).

For this exercise, do the following: 

1. The TEI exercise found [in our supporting materials](../supporting materials/tei.md).

I will note that a perfectly fine final project for HIST3814 might be to use this exercise as a model to markup the war diary and suggest ways this material might be explored. Remember to make (and lodge in your repository) a file detailing the work you've done and any issues you've run into.

-----

## Exercise 4: APIs

Sometimes, a website will have what is called an **Application Programming Interface** or API. In essence, this lets a program on your computer talk to the computer serving the website you're interested in, such that the website gives you the data that you're looking for.

That is, instead of **you** punching in the search terms, and copying and pasting the results, you get the computer to do it. More or less. The thing is, the results come back to you in a machine-readable format &mdash; often, JSON, which is a kind of text format. It looks like the following:

![Image showing JSON formating](http://i.imgur.com/LtZWyle.png)

This exercises uses an [O-Date Binder](https://o-date.github.io/draft/book/using-application-programming-interfaces-apis-to-retrieve-data.html).

Launch the [jupyter binder](http://mybinder.org/v2/gh/o-date/open-context-jupyter/master). 

1. Open the 'Chronicling America API' notebook. Run through its various steps so that you end up with a json file of results. Imagine that you are writing a paper on the public reception of archaeology in the 19th century in the United States. Alter the notebook so that you can find primary source material for your study. **Going further:** Find another API for historical newspapers somewhere else in the world. Duplicate the notebook, and alter it to search this other API so that you can have material for a cross-cultural comparison.
2. Open the 'Open Context API'. Notice how similar it is to the first notebook! Run through the steps so that you can see it work. Study the Open Context [API documentation](https://opencontext.org/about/services). Modify the search to return materials from a particular project or site.
3. The final notebook, 'Open Context Measurements', is a much more complicated series of calls to the Open Context API (courtesy of Eric Kansa). In this notebook, we are searching for zoological data held in Open Context, using standardised vocabularies from that field that described faunal remains. Examine the code carefully - do you see a series of nested 'if' statements? Remember that data is often described using JSON attribute:value pairs. These can be nested within one another, like Russian dolls. This series of 'if' statements parses the data into these nested levels, looking for the faunal information. Open Context is using an _ontology_ or formal description of categorization of the data (which you can visit [on the Open Context website](https://opencontext.org/vocabularies/open-context-zooarch/)) that enables inter-operability with various Linked Open Data schemes. Run each section of the code. Do you see the section that defines how to make a plot? This code is called on later in the notebook, enabling us to plot the counts of the different kinds of faunal data. Try plotting different categories.
4. The notebooks above were written in Python. We can also interact with APIs using the R statistical programming language. The [Portable Antiquities Scheme database](http://finds.org.uk) also has an API. Launch this [binder](https://mybinder.org/v2/gh/o-date/notebooks-archdata/master) and open the 'Retrieving Data from the Portable Antiquities Scheme Database' notebook (courtesy of Daniel Pett). This notebook is in two parts. The first frames a query and then writes the result to a csv file for you. Work out how to make the query search for medieval materials, and write a csv to keep more of the data fields.
5. The second part of the notebook that interacts with the Portable Antiquities Scheme database uses that csv file to determine where the images for each item are located on the Scheme's servers, and to download them.

Going further - the [Programming Historian](https://programminghistorian.org/) has a lesson on [creating a web API](https://programminghistorian.org/en/lessons/creating-apis-with-python-and-flask). Follow that lesson and build a web api that serves some archaeological data that you've created or have access to. One idea might be to extend the [Digital Atlas of Egyptian Archaeology](https://msu-anthropology.github.io/daea/), a gazetteer created by [Anthropology undergraduates at Michigan State University](http://leadr.msu.edu/projects/fall-2014-3/daea/). The source data may be found [on the MSU Anthropology GitHub page](https://github.com/msu-anthropology/daea/blob/master/sites-popup.csv). 

-----

## Exercise 5: Mining Twitter

This exercise mines Twitter for tweets, photos, etc, connected to bad archaeology.

You will require the following on your machine:

1. Twitter account
2. Python installed on your machine

However, we will use a virtual computer that already has Python and the `Twarc` (TWitter ARChiver) package already installed. (Mac users: you **do** have python already on your machine; Windows users, you don't. So, to make life easier, I built you all a virtual computer. Read on, this will make sense.)

Twarc was created by Ed Summers, who is heading a project called [Documenting the Now](https://www.docnow.io/) to create the tools necessary to keep track of all the ways our media are disseminating (and distorting!) the truth. It's a rapid-response suite of tools to capture events as they happen.

What we're going to do is set up some credentials with Twitter that give you access to the underlying data of the tweets. Then, the Twarc packages has a bunch of functions built in that lets you search and archive tweets.

### Setting up your Twitter Credentials

**WARNING &mdash; Update as of October 12, 2018:** It seems that Twitter now requires some kind of developer authentication process now. So the instructions below might have extra steps. If that's the case, no problem &mdash; [email Dr Graham](mailto:ShawnGraham@cunet.carleton.ca) for his consumer secret/key.

**READ THROUGH FIRST, THEN START &mdash; If you do not want to set up a Twitter account/developer app page, skip to [Part Two: Firing Up Your Virtual Computer](../Exercises/#part-two-firing-up-your-virtual-computer)**

1. First of all, you need to set up a Twitter account. If you do not have a [Twitter account](http://twitter.com), sign-up, but make sure to minimize any personal information that is exposed. For instance, do not make your handle the same as your real name.

    + Turn off geolocation. Do not give your actual location in the profile.

    + View the settings, and make sure all of the privacy settings are dialed down. For the time being, you do have to associate a cell phone number with your account. You can delete that once you've done the next step.

2. Go to the [Twitter apps page - https://apps.twitter.com/](https://apps.twitter.com/) and click on 'New App'.

3. On the New Application page, just give your app a name like `my-twarc` or similar. For the portion labelled 'Website', use my Crafting Digital History site URL, `site.craftingdigitalhistory.ca` (although for our purposes any website will do). You don’t need to fill in any of the rest of the fields.

4. Continue on to the next page (tick off the box saying you’ve read the developer code of behaviour). This next page shows you all the details about your new application.

5. Click on the tab labelled `Keys and Access Tokens`.

6. Copy the 'Consumer Key (API Key)' (the consumer secret) to a text file.

7. Click on the button labelled `Create Access Tokens` at the bottom of the page. This generates an access token and an access secret.

8. Copy those to your text file and save it. **Do not put this file in your repo or leave it online anywhere. Otherwise, a person can impersonate you!**

![Image showing set-up for Twitter's Application settings](http://i.imgur.com/mM4hZNN.png)

### Part Two: Firing Up Your Virtual Computer

1. **Right-click** the following Binder link and select `Open in new tab`: [![Binder](https://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/o-date/social-media-work/master)

2. Wait. It is setting up your new virtual computer. When it's loaded up, it will resembled the following image:
![Image showing the jupyter layout, saying not to click the Quit or logout buttons, that clicking the jupyter logo will refresh the page, and that you can click the dropdown labelled New and select the Terminal](http://www.screencast-o-matic.com/screenshots/u/e7i1/1539304640402-48607.png)

3. Click the 'New' button, and select 'Terminal'. You should see something resembling the following image:
![Image showing the terminal in jupyter, saying to click the black area to make the window active](http://www.screencast-o-matic.com/screenshots/u/e7i1/1539304810966-61987.png)

**WARNING. You have to interact with the virtual computer &mdash; type a command, click on something &mdash; within ten minutes or it shuts down and you lose everything**.

**Pro tip:** you can always type `$ pwd` into the terminal as a way of keeping the thing alive. This command Prints the Working Directory (ex. tells you what folder you're in).

4. Type `$ twarc configure` into the terminal.

![Image showing the terminal in jupyter, saying to type twarc configure, hit enter, and then enter the consumer key from the Twitter app settings](http://www.screencast-o-matic.com/screenshots/u/e7i1/1539304902569-2152.png
)

And in the next screenshot, read the annotations from top to bottom:

![Image showing the terminal in jupyter, saying to enter the Consumer Key and Consumer secret and then to open the twitter API URL the terminal outputs](http://www.screencast-o-matic.com/screenshots/u/e7i1/1539305146992-49673.png)

But where is this 'Displayed pin'? It's in the window in your browser where the 'Authenticate Twitter?' dialogue was displayed. Instead of the twitter page, the URL you gave way up in part one step 3 has now been loaded and the information you need is indicated with `oauth_token=`. You need the bit after the `=` sign.

![Image showing a browser where the secret API URL from the previous image was pasted, permitting you to authorize the app](http://www.screencast-o-matic.com/screenshots/u/e7i1/1539305692926-702.png)

It will resemble something like `-bBafl42aabB...` etc., a long string of numbers and letters. Copy the entire string.

Then paste it in:
![Image showing the terminal in jupyter, saying that the app has been authorized and twarc is ready](http://www.screencast-o-matic.com/screenshots/u/e7i1/1539305848359-8369.png)

And you're ready to data mine twitter!

### Part Three: Find some stuff

On the [Twarc README page](https://github.com/DocNow/twarc) there are examples of how to use Twarc to search for information.

If you typed in `$ twarc search electricarchaeo` and hit return, the terminal window would fill with tweet metadata and data; it'd take about one or two minutes to run as I'm pretty active on twitter (watch [a video of Twarc in action](https://screencast-o-matic.com/watch/cF6lVjY05K)). **But this is only the last week or so of information!** You can save this information to a file instead of your terminal window by typing the following command into the terminal:

`$ twarc search electricarchaeo > electricarchaeo.jsonl`  (that's a lower case 'L' at the end of `.json`)

If you then right-click on the 'jupyter' logo at the top of the screen and open the link in a new window, you'll be back at the File Explorer. One of the files listed will be the new `electricarchaeo.jsonl` file you made.

![Image showing the full JSON file in jupyter of eletric archaeo's tweets](http://www.screencast-o-matic.com/screenshots/u/e7i1/1539306896907-33928.png)

So what can we do with this information? Quite a lot, but for now, let's make a basic word cloud of the text of the tweets.

We're going to need some utilities that Ed Summer has written, some extra python programs that can work with this information. Navigate to the terminal window and type the command `$ git clone https://github.com/DocNow/twarc`.

This tells the `git` program that's already installed to go to GitHub and get the source code for Twarc. One of the folders it is going to grab is called `utils` and that has the utility program for making a word cloud that we will use.

We will now type in the location and name of the program we want to use, followed by the data to operate on, followed by the name of the output file we want to create. Type `$ twarc/utils/wordcloud.py electricarchaeo.jsonl > wordcloud.html` into the terminal.

Notice that when you press enter, nothing seems to happen. Go back to the list of files (right-click the jupyter logo and select `Open in new tab`) and one of the files listed will be `wordcloud.html`. Click on that file.

![Image showing the created word cloud from the JSON data](http://www.screencast-o-matic.com/screenshots/u/e7i1/1539307355837-46159.png)

(If you reload the page, the word-cloud will regenerate, different colours, positions)

### Download the data you collected.

Once this virtual computer shuts down, all of that data you collected will be lost. Click on the jupyter logo, select the files you want to keep, and hit download.

![Image showing the jupyter binder, saying to check the box next to the jsonl file and click the button labelled download. Note the file may be large](http://www.screencast-o-matic.com/screenshots/u/e7i1/1539307991802-92070.png)

Depending on your browser, you might get a warning, asking if you're sure you want to download. Click Yes/OK.

### Other things you could do

Descriptions of what the other utilities do can be found on the [Twarc GitHub repository](https://github.com/DocNow/twarc).

Go, play! Once you've got that `jsonl` file, you could convert it to `csv` and then import it into a spreadsheet tool like Excel of Google Sheets. The [JSON to CSV website](https://json-csv.com/) can also do that conversion for you. **Warning:** there is a 1MB limit for using the JSON to CSV tool. If your data is too big, we'll find something else &mdash; perhaps a bit of code or a utility that we can use on the command line (ex. read [Gabriel Pires' Medium article on using Python to convert JSON to CSV](https://medium.com/@gabrielpires/how-to-convert-a-json-file-to-csv-python-script-a9ff0a3f906e)). 

With a bit of effort, you can make a network graph of who responds to who. Or explore tweeting by gender. Or map tweets. Or... or... or.

Probably the easiest thing you could do, once you've converted to `csv` (again, the [JSON to CSV website can do this](https://json-csv.com/)), is to copy the column of tweet text itself into a tool like [Voyant](http://voyant-tools.org). Why not give that a try? 

What you do really depends on what kinds of questions you're hoping to answer. Now that you have access to the firehose of data that is Twitter, what kinds of things might you like to know? How do people talk about archaeology? How do they talk about Atlantis?

#### What can you do with this data?

1. Examine the Twarc repository, especially its utilities. You could extract the geolocated ones and map them. You could examine the difference between 'male' and 'female' tweeters (and how problematic might that be?). 

2. In your CSV, save the text of the posts to a new file and upload it to something like [Voyant Tools](http://voyant-tools.org) to visualize trends over time. 

3. Google for analysis of Twitter data to get some ideas.

-----

## Exercise 6: Using Tesseract to turn an image into text

We've all used image files like JPGs and PNGs. Images always look the same on whatever machine they are displayed on, because they contain within themselves the complete description of what the 'page' should look like. You're likley familiar with the fact that you cannot select text within an image. When we digitize documents, the image that results only contains the image layer, not the text. 

To turn that image into text, we have to do what's called 'object character recognition', or OCR. An OCR algorithm looks at the pattern of pixels in the image, and maps these against the shapes it 'knows' to be an A, or an a, or a B, or a &, and so on. Cleaner, sharper printing gives better results as do high resolution images free from noise. People who have a lot of material to OCR use some very powerful tools to identify blocks of text within the newspaper page, and then train the machine to identify these, a process beyond us just now (but visit [this Tesseract q & a on stackoverflow](https://stackoverflow.com/questions/28591117/how-do-i-segment-a-document-using-tesseract-then-output-the-resulting-bounding-b#28640570) if you're interested).

In this exercise, you'll:

+ Install the Tesseract OCR engine into your DH Box
+ Install and use ImageMagick to convert the JPG into TIFF image format
+ Use Tesseract to OCR the resulting pages.
+ Use Tesseract in R to OCR the resulting pages.
+ Compare the resulting OCRd texts.
 
### Converting images in the command line

1. Begin by making a new directory for this exercise: `$ mkdir ocr-test`. 

2. Type `$ cd ocr-test` to change directories into ocr-test.

3. Type `$ sudo apt-get install tesseract-ocr` to grab the latest version of Tesseract and install it into your DH Box. Enter your password when the computer asks for it.

4. Type `$ sudo apt-get install imagemagick` to install ImageMagick.

5. Let's convert the first file to TIFF with ImageMagick's convert command

        $ convert -density 300 ~/war-diary/e001518087.jpg -depth 8 -strip -background white -alpha off e001518087.tiff

    You want a high density image, which is what the -density and the -depth flags do; the rest of the command formats the image in a way that Tesseract expects to encounter text. This command might take a while. Just wait, be patient.

6. Extract text with `$ tesseract e001518087.tiff output.txt`. This might also take some time.

7. Download the `output.txt` file to your own machine via DH Box's filemanager. 

8. Open the file with a text editor. 

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/cIC3vRI6TYM?rel=0" title="Converting an image to text using the command line" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

### Converting images in R

1. Now we will convert the file using R. Navigate to RStudio in the DH Box.

2. On the upper left side, click the green plus button > R Script to open a new blank script file.

3. Paste in the following script and save it as `ocr` in RStudio.

        install.packages('magick')
        install.packages('magrittr')
        install.packages('pdftools')
        install.packages('tesseract')
        library(magick) 
        library(magrittr)
        library(pdftools)
        library(tesseract)
        text <- image_read("~/war-diary/e001518087.jpg") %>% 
          image_resize("2000") %>% 
          image_convert(colorspace = 'gray') %>% 
          image_trim() %>% 
          image_ocr()
        write.table(text, "~/ocr-test/R.txt")

    The above script first installs three packages to RStudio, Magick, Magrittr, and Tesseract. Magick processes the image as high quality; Magrittr uses the symbols `%>%` as a pipe that forces the values of an expression into the next function (allowing our script to perform it's conversion in steps); Tesseract is the actual OCR engine that converts our image to text. Then the script loads each package. Lastly, the script processes the image, OCRs the text, and writes it to a `txt` file.

    Before installing any packages in the DH Box RStudio, we need to install some dependencies in the command line. The reason is that since DH Box runs an older version of RStudio, not everything installs as planned compared to the desktop RStudio.

4. Type `$ sudo apt-get install libcurl4-gnutls-dev` in the command line to install the libcurl library (this installs RCurl).

5. Type `$ sudo apt-get install libmagick++-dev ` in the command line to install the libmagick library.

6. Type `$ sudo apt-get install libtesseract-dev` in the command line to install the libtesseract library.

7. Type `$ sudo apt-get install libleptonica-dev` in the command line to install the libleptonic library.

8. Type `$ sudo apt-get install tesseract-ocr-eng` in the command line to install the English Tesseract library.

9. Type `$ sudo apt-get install libpoppler-cpp-dev` in the command line to install the poppler cpp library.

10. Navigate to RStudio and run each `install.packages` line in our script. This will take some time.

11. Run each `library()` line to load the libraries.

12. Run each line up to `image_ocr()`. This may take some time to complete.

13. Run the last line `write.table()` to export the OCR to a text file with the same name.

14. Navigate to your file manager and download both the `output.txt` file and the `R.txt` file.

15. Compare the two text files in your desktop. How is the OCR in the command line versus within R? Note that they both use Tesseract just with different settings and in different environments. 

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/2jAmfNdMdpk?rel=0" title="Converting an image to text using RStudio" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

### Progressively converting our files with Tesseract

1. Now take a screen shot of both text files (just the text area) and name them `output_1.png` and `R_1.png` respectively.

2. Upload both files into DH Box via the File Manager.

3. In the command line, type `$ tesseract output_1.png output_1.txt`. 

4. In RStudio, change the file paths in your script to the following:
 
        text <- image_read("~/ocr-test/R_1.png") %>% 
          image_resize("2000") %>% 
          image_convert(colorspace = 'gray') %>% 
          image_trim() %>% 
          image_ocr()
        write.table(text, "~/ocr-test/R_1.txt")

5. Run each script line again. Except this time **DO NOT** run the `install.packages()` lines since we already installed them. Simply load the libraries again and run each line.

6. Navigate to the File Manager and download `ouput_1.txt` and `R_1.txt`.

7. Compare these two files. Did the OCR conversion get progressively worse? How do they compare to each other, to the first attempt at conversion, and then to the originals?

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/C6QasGX6Ncw?rel=0" title="Converting our images further" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

8. Choose either the command line or the R method to convert more of the war diary files to text. Save these files into a new directory called `war-diary-text`. We will use these text files for future work in topic modeling and text analysis. How might your decision on which method to use change the results you would get in, say, a topic modeling tool?

    **Hint:** Check below for [a way to automate the conversion process](#batch-converting-image-files).

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/puUNq1qzFmY?rel=0" title="Converting the war diary files to text using RStudio" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

Think about how these conversions can change based on the image being run through Tesseract. Does Tesseract have an easier time converting computer text even though it's in an image format? How might OCR conversions affect the way historians work on batch files? How does the context of the text change how historians analyse it? 

Look up the [Tesseract wiki](https://github.com/tesseract-ocr/tesseract/wiki/Command-Line-Usage). What other options could you use with the Tesseract command to improve the results? When you decide to download Tesseract to you own computer, use the following two guides to automating bulk OCR (multiple files) with Tesseract: [Peirson's](https://diging.atlassian.net/wiki/display/DCH/Tutorial%3A+Text+Extraction+and+OCR+with+Tesseract+and+ImageMagick) and [Schmidt's](http://benschmidt.org/dighist13/?page_id=129).

### Batch converting image files

Now that you've learned to convert image files to text individually, you should know that there is a quicker way to do this. The following script takes your Canadian war diary `jpg` image files and OCRs them using the same process as above. However this time, the `function(i)` (`i` stands for iterate), goes through the folder for each `jpg` file and converts them to a `png` file into a text file with the suffix `-ocr.txt` until it notes there are no more image files to convert. The converted files will output to the same folder, in our case `war-diary`. 

        library(magick) 
        library(magrittr)
        library(pdftools)
        library(tesseract) 

        dest <- "/war-diary"
        myfiles <- list.files(path = dest, pattern = "jpg", full.names = TRUE)
         
        # improve the images
        # ocr 'em
        # write the output to text file
         
        lapply(myfiles, function(i){
            text <- image_read(i) %>%
            image_resize("3000x") %>%
            image_convert(type = 'Grayscale') %>%
            image_trim(fuzz = 40) %>%
            image_write(format = 'png', density = '300x300') %>%
            tesseract::ocr()
         
        outfile <- paste(i,"-ocr.txt",sep="")
        cat(text, file=outfile, sep="\n")
         
        })

You can probably understand now why this method works much better than the previous R script: we automate our process (ie. we run the script just once and it iterates through the folder for us), append a suffix to the txt file name noting the OCRd text, and output it all to the same folder.

Keep these files somewhere handy on your computer! We will use them throughout the course.

By iterating through the folder, we have created a loop. Loops can be a very powerful tool for Digital Historians, as we can begin to automate processes that would take much longer by hand. Read more about ['for loops' on the R-blogger website](https://www.r-bloggers.com/how-to-write-the-first-for-loop-in-r/).

**NB** The above script processes dozens of images and may take quite a bit of time to complete. 

## Reference

Part of this tutorial was adapted from [The Programming Historian](https://programminghistorian.org) released under the CC-BY license, including:

Ian Milligan, "Automated Downloading with Wget," The Programming Historian 1 (2012), [https://programminghistorian.org/lessons/automated-downloading-with-wget](https://programminghistorian.org/lessons/automated-downloading-with-wget).

Kellen Kurschinski, "Applied Archival Downloading with Wget," The Programming Historian 2 (2013), [https://programminghistorian.org/lessons/applied-archival-downloading-with-wget](https://programminghistorian.org/lessons/applied-archival-downloading-with-wget).

[Twitter user 'superboreen' on R OCR](https://twitter.com/superboreen/status/958418116324790273).
