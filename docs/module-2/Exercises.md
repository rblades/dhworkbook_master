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

Digitization requires human intervention. This can be as straightforward as correcting errors or adjusting the scanner settings when we do OCR, or it can be the rather more involved work of adding a layer of semantic information to the text. When we mark up a text with the semantic hooks and signs that explain we are talking about **London, Ontario** rather than **London, UK**, we've made the text a whole lot more useful for other scholars or tools. In this exercise, you will do some basic marking up of a text using standards from the [Text Encoding Initiative](http://www.tei-c.org/index.xml). (Some of the earliest digital history work was along these lines). 

The TEI exercise requires careful attention to detail. Read through it before you try it. In this exercise, you'll transcribe a page from an abolitionist's pamphlet. You'll also think about ways of transforming the resulting XML into other formats. Make notes in a file to upload to your repository, and upload your XML and your XSL file to your own repository as well. (As an added optional challenge, create a gh-pages branch and figure out the direct URL to your XML file, and email that URL to me).

For this exercise, do the following: 

1. The TEI exercise found [in our supporting materials](../supporting materials/tei.md).

I will note that a perfectly fine final project for HIST3814 might be to use this exercise as a model to markup the war diary and suggest ways this material might be explored. Remember to make (and lodge in your repository) a file detailing the work you've done and any issues you've run into.

-----

## Exercise 4: APIs

Sometimes, a website will have what is called an **Application Programming Interface** or API. In essence, this lets a program on your computer talk to the computer serving the website you're interested in, such that the website gives you the data that you're looking for.

That is, instead of **you** punching in the search terms, and copying and pasting the results, you get the computer to do it. More or less. The thing is, the results come back to you in a machine-readable format &mdash; often, JSON, which is a kind of text format. It looks like the following:

![Image showing JSON formating](http://i.imgur.com/LtZWyle.png)

The [**Canadiana Discovery Portal**](http://search.canadiana.ca/) has tonnes of materials related to Canada's history, from a wide variety of sources.

1. Go to the [**Canadiana Discovery Portal**](http://search.canadiana.ca/), and search "ottawa".

2. Set the date range to 1800 to 1900 and hit enter. You are presented with a page of results -56 249 results! That's a lot of data. But do you notice the address bar of your browser? It'll say something like this:

        http://search.canadiana.ca/search?q=ottawa&field=&df=1800&dt=1900

    Your search query has been put into the URL. You're looking at the API! Everything after `/search` is a command that you are sending to the Canadiana server.

3. Scroll through the results, and you'll see a number just before the question mark `?`

        http://search.canadiana.ca/search/2?df=1800&dt=1900&q=ottawa&field=
        http://search.canadiana.ca/search/3?df=1800&dt=1900&q=ottawa&field=
        http://search.canadiana.ca/search/4?df=1800&dt=1900&q=ottawa&field=

    ....all the way up to 5625 (ie. 10 results per page, so 56249 / 10).

    If you go to the [Canadiana API support page](http://search.canadiana.ca/support/api) you can see the full list of options. What we are particularly interested in now is the bit that says `&fmt=json`.

4. Add that `&fmt=json` to your query URL. How different the results now look! What's nice here is that the data is formatted in a way that makes sense to a machine &mdash; which we'll learn more about in due course.

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/-eNAcimCHsA?rel=0" title="Introduction to the Canadiana API" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

    If you look back at the full list of API options, you'll see at the bottom that one of the options is 'retrieving individual item records'; the key for that is a field called **oocihm**. If you look at your page of JSON results, and scroll through them, you'll see that each individual record has its own oocihm number. If we could get a list of those, we'd be able to programmatically slot them into the commands for retrieving individual item records:

        http://search.canadiana.ca/view/oocihm.16278/?r=0&s=1&fmt=json&api_text=1

    The problem is: how to retrieve those oocihm numbers. The answer is, 'we write a program'. And the program that you want can be [found on Ian Milligan's website](http://ianmilligan.ca/api-example-sh/). Study that program carefully. There are a number of useful things happening in there, notably **curl**, **jq**, **sed**, and **awk**. **curl**  is a program for downloading webpages, **jq** for dealing with JSON, and **sed** and **awk** for searching within and cleaning up text. If this all sounds Greek to you, there is an excellent gentle introduction over at [William Turkel's blog](http://williamjturkel.net/2013/06/15/basic-text-analysis-with-command-line-tools-in-linux/).

5. We need the command line program jq. We install it into our DH Box with `$ sudo apt-get install jq -y`

6. We need to create a program. Make a new directory for this exercise like so: `$ mkdir m2e4`. Then, change into that directory by typing `$ cd m2e4`. 

7. Make sure that's where you are by typing `$ pwd`. Now, make an empty file for our program with `$ touch canadiana.sh`. Touch makes an empty file; the `.sh` in the filename indicates that this is a shell script.

8. Open the empty file with `$ nano canadiana.sh`. Now, the program that Ian Milligan wrote makes calls to the API that **used to live** at `eco.canadiana.ca`. But note the [error message on Canadiana's website](http://eco.canadiana.ca/view/oocihm.16278/?r=0&s=1&fmt=json&api_text=1). So we have to change Milligan's script so that it points to the API at [search.canadiana.ca](http://search.canadiana.ca/). Copy the script below into your empty `canadiana.sh`. If you want, adjust the search parameters (in the line starting with `pages`) for material you're more interested in.

        #! /bin/bash
        pages=$(curl 'http://search.canadiana.ca/search?q=ottawa*&field=&so=score&df=1800&dt=1900&fmt=json' | jq '.pages')
        # this goes into the results and reads the value of 'pages' in each one of them.
        # it then tells us how many pages we're going to have.
        echo "Pages:"$pages
        # this says 'for each one of these pages, download the 'key' value on each page'
        for i in $(seq 1 $pages)
        do
                curl 'http://search.canadiana.ca/search/'${i}'?q=ottawa*&field=&so=score&df=1800&dt=1900&fmt=json' | jq '.docs[] | {key}' >> results.txt
        done
        # the next two lines take the results.txt file that is quite messy and clean it up. I'll try to explain what they all mean. Basically, tr deletes a given character - so we delete quotation marks "\"" (the slash tells the computer not to treat the quotation mark as a computer code, but as a quotation mark itself), to erase spaces, and to find the phrase "key:" and delete it too.
        sed -e 's/\"key\": \"//g' results.txt | tr -d "\"" | tr -d "{" | tr -d "}" | tr -s " " | sed '/^\s*$/d' | tr -d ' ' > cleanlist.txt
        # this adds a prefix and a suffix.
        awk '$0="search.canadiana.ca/view/"$0' cleanlist.txt| awk '{print $0 "/1?r=0&s=1&fmt=json&api_text=1"}' > urlstograb.txt
        # then if we want we can take those URLs and output them all to a big text file for analysis.
        wget -i urlstograb.txt -O output.txt

9. Hit ctrl+x to exit Nano, and save the changes.

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/5ya8m-A6Lrs?rel=0" title="Writing a bash script with the command line" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

10. Before we can run this program, we have to tell DH Box that it is alright to run it. To change the 'permissions' on the file, type `$ chmod 755 canadiana.sh`

    The `$ chmod` command means change mode. Each number represents a user permission for reading, writing, and executing files on your computer.  

11. And now we can run the program by typing `$ ./canadiana.sh` (the ./ is important!)

    Ta da! You now have a pretty powerful tool for grabbing data from one of the largest portals for Canadian history! 

12. Download your `output.txt` file to your computer via the file manager and have a look at it. 

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/J2AZZs1uRuc?rel=0" title="Accessing the Canadiana API with a command line script" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

Make sure to make a file noting what you've done, commands you've made, etc, and upload it in your GitHub repository.

-----

## Exercise 5: Mining Twitter

Ed Summers is part of a project called '[Documenting the Now](http://www.docnow.io/)' which is developing tools to collect and understand the historical materials being shared (and lost) on social media. One component of Documenting the Now is the Twitter Archiving Tool, '[Twarc](https://github.com/DocNow/twarc)'. In this exercise, you are going to use Twarc to create an archive of Tweets relevant to a current trending news topic.

1. First of all, you need to set up a Twitter account, if you haven't already got one. Do so, but make sure to minimize any personal information that is exposed. For instance, don't make your handle the same as your real name. 

2. Turn off geolocation. Do not give your actual location in the profile. 

3. View the settings, and make sure all of the privacy settings are dialed down. For the time being, you **do** have to associate a cell phone number with your account. You can delete that once you've done the next step.

4. Go to the [Twitter apps page](https://apps.twitter.com/) and click on **new app**. 

5. On the **new application** page, just give your app a name like **my-twarc** or similar. For website, use the [Crafting Digital History site URL](http://site.craftingdigitalhistory.ca/) (although for our purposes any website will do). You don’t need to fill in any of the rest of the fields. 

6. Continue on to the next page (tick off the box saying you’ve read the developer code of behaviour). This next page shows you all the details about your new application.

7. Click on the ‘Keys and Access Tokens’ tab. 

8. Copy the consumer key, the consumer secret to a text file.

9. Click on the ‘create access tokens’ button at the bottom of the page. This generates an access token and an access secret. 

10. Copy those to your text file, save it. **Do not put this file in your repo or leave it online anywhere** 
    
    ![Image showing Twitter access tokens](http://i.imgur.com/mM4hZNN.png)

11. We need to download an older version of Twarc to work with the DH Box. In your DH Box, at the command line, type the following:

        $ sudo pip install https://github.com/DocNow/twarc/archive/v1.2.0.tar.gz

    Twarc is written in Python, which is already installed in DH Box. 'Pip' is a package manager for installing new Python modules and packages. 

12. Now type `$ twarc configure ` and give it the information it asks for (your consumer secret etc).

    You're now ready to search. For instance, `$ twarc search canada150 > search.json` will search Twitter for posts using the canada150 hashtag. 

    **Wait! Don't run that command! (Force-stop the search by hitting ctrl+c.)** 

    If you search for `canada150` , there are, what, 36 million Canadians? How many tweets is that likely to be? Quite a lot &mdash; and the command will run quietly for days grabbing that information, writing it to file, and you'll be sitting looking at the screen wondering if anything is happening. 

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/K6boXV_AzMc?rel=0" title="Mining data from Twitter with the command line" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

13. Try something smaller and more contained for now: `$ twarc search hist3814o > search.json`. 

    **Note that Twitter only gives access to the last two weeks or so via search.** For grabbing the stream **as an event happens** you'd use the `twarc stream` command &mdash; see the Twarc documentation for more.

    It might take some time for the search to happen. **You can always force-stop the search by hitting ctrl+c.** If you do that though there could be an error in the formatting of the file which will throw an error when you get to step 15. You can still open the JSON in a text editor though, but you will have to go to the end of the file and fix the formatting.

    The data being collected is in JSON format. That is, a list of 'keys' and 'values'. This is a handy format for computers, and some data visualization platforms require data in this format. For our purposes we might want to transform the JSON into a CSV (comma separated) table &mdash; a spreadsheet.

14. Type `$ sudo npm install json2csv --save -g`. This installs a command that can convert the JSON to CSV format. Full details about the command can be found on [json2csv's GitHub repository](https://github.com/zemirco/json2csv#command-line-interface).

15. Convert your `search.json` to CSV by typing `json2csv -i search.json -o out.csv`

16. Examine your data either in a text editor or in a spreadsheet.

17. Use Twarc to create a file with a list of IDs. 

18. Lodge this list and your history and notes in your repository.

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/I5zbYl-Lxf4?rel=0" title="Mining data from Twitter with the command line" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

**NB Twitter forbids the sharing of the full metadata of a collection of tweets. You may however share a list of tweet IDs. See the Twarc documentation for the instructions on how to do that.**

### What can you do with this data?

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
