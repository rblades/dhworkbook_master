# Module 4 Exercises

There are **many** [different tools and approaches](http://dhresourcesforprojectbuilding.pbworks.com/w/page/69244314/Tutorials%20for%20DH%20Tools%20and%20Methods) you could use to visualize your data, both as a preliminary pass to spot the holes and also for more formal analysis. In which case, for this module, I would like you to select **two** of these exercises which seem most germane for your final project.

You are welcome to work through more of them, of course, but I want the exercises to move your own research forward. Some of these I wrote and some are adapted from [The Macroscope](http://themacroscope.org); others are adapted or used holus-bolus from scholars like [Miriam Posner](http://miriamposner.com/blog/), [Fred Gibbs](http://fredgibbs.net/), and [Heather Froehlich](http://hfroehli.ch/) (and I'm grateful that they shared their materials!). Finally, you are welcome to explore the lessons and tutorials at [The Programming Historian](http://programminghistorian.org/lessons/) if they seem appropriate to what you want to do for your project.

**But what if I haven't any idea of what to do for the final project?** Then read through the various tutorials for inspiration. Find something that strikes you as interesting, and then talk to me about how you might employ the ideas or concepts with regard to the Equity data.

## Things to install?

Many of these involve having to install more software on your own machine. In those exercises that involve using R and RStudio, you are welcome to install RStudio on your own machine OR to use it in DHBox. Please read [this quick introduction to R and Rstudio carefully](../supporting materials/quick-intro-r.md).

**If you decide to install R and RStudio on your own machine,** I would suggest you read the introductory bits from Lincoln Mullen's book-in-progress, [Computational Historical Thinking](http://dh-r.lincolnmullen.com/getting-started.html), especially the 'setup' part under 'getting started' (pay attention to the bit on installing packages and dependencies). If you spot any exercises in Mullen's book that seem relevant to your project, you may do those as an alternative to the ones here. *Alternatively*, go to [Swirl](http://swirlstats.com/) and [learn the basics of R within R](http://swirlstats.com/students.html). [DHNow](http://digitalhumanitiesnow.org/2016/01/resource-basic-text-mining-in-r/) links to a new [Basic Text Mining in R](https://web.archive.org/web/20160309170928/https://rstudio-pubs-static.s3.amazonaws.com/31867_8236987cf0a8444e962ccd2aec46d9c3.html) tutorial which is worth checking out as well.

**NB It is always very important to record in your own notebooks what version of R you used for your analysis, what version of any R packages you installed and used, and so on because packages can go out of date.**

In the table below I've gathered the exercises together under the headings of **Text**, **Networks**, **Maps**, and **Charts**. I've also added some entries that I am categorizing under **Art** The first is a series of exercises on [the sonification of data](http://programminghistorian.org/lessons/sonification) and the second is a guide [to making twitterbots](https://programminghistorian.github.io/ph-submissions/lessons/intro-to-twitterbots); the third is about glitching digital imagery. These approaches can provide surprising and novel insights into history, as they move from representing history digitally to **performing** it. See for instance the final project in an undergraduate digital history class at the University of Saskatchewan by [Daniel Ruten](https://danielruten.wordpress.com/2017/04/15/sonic-word-clouds-an-experiment-with-data-sonification-part-i-introduction/) where he translated simple wordclouds of a WWI diary into a profound auditory performance. I would be very interested indeed to see if any final projects in HIST3814o gave sonification or twitterbots or glitch a try.

| Texts        | Networks         | Maps  | Charts | Art |
| ------------- |:-------------:|:-----:|:--------:|--------:|
| [Topic Modeling Tool](#exercise-2)  |[Network analysis in Gephi](#exercise-1) |[Simple mapping & georectifying](#exercise-8) |[Quick charts using RAW](#exercise-7) |[Sonification](#exercise-10)|
| [Topic Modeling in R](#exercise-3)  |[Converting 2-mode to 1-mode](../supporting materials/multimode-networks.txt.md) |[QGIS (tutorials by Fred Gibbs)](#exercise-10) | |[Twitterbots](#exercise-11)|
| [Text Analysis with OverviewProject](#exercise-4)   |[Network Analysis in R](#exercise-9) |[Geoparsing with Python](../supporting materials/geoparsing-w-python.txt.md) | |[Glitching Photos](../supporting materials/glitch.md) |
| [Corpus Linguistics with AntConc](#exercise-5)  |[Network Analysis in Cytoscape](https://github.com/miriamposner/cytoscape_tutorials)|[Palladio with Posner](http://miriamposner.com/blog/getting-started-with-palladio/) | | |
| [Text Analysis with Voyant](#exercise-6)    |[Choose your own adventure](../supporting materials/cyoa.txt.md)|[Leaflet.js Maps](../supporting materials/leaflet.txt.md) | | |
| | | | | |

----------------------

## Exercise 1: Network Visualization

This exercise uses the open source programme **Gephi** which you install on your own computer. If you'd rather not install anything, please see [Network Analysis in R](#exercise-9) instead.

Recall that the index of the collected letters of the Republic of Texas was just a list of letters from so-and-so to so-and-so. We haven't looked at the content of those letters, but the shape of network - the meta data of that correspondence - can be revealing (remember [Paul Revere!](https://kieranhealy.org/blog/archives/2013/06/09/using-metadata-to-find-paul-revere/)) When we stitch that together into a network of people connected because they exchanged letters, we end up with a shard of their social network. Networks can be queried for things like power, position, and role, and so used judiciously, we can begin to suss something of the social structures in which their history took place. I would recommend that you also take a long look at Scott Weingart's series, [Networks Demystified](http://scottbot.net/networks-demystified-9-modality/). Finally, [heed our warning](http://www.themacroscope.org/?page_id=449).

In this exercise, you will transform your Texan Correspondence data into a network, which you will then visualize with the open source programme **Gephi** The detailed instructions are [in our supporting materials](../supporting materials/gephi.txt.md).

-----

## Exercise 2: Topic Modeling Tool
In exercise 2, you will use the **Topic Modeling Tool** to create a simple topic model and a webpage that allows you to browse the results.

1. Download the [topic modeling tool from Github](https://github.com/senderle/topic-modeling-tool).
2. Make sure you have some content on your own machine; the Colonial Newspaper Database is a handy corpus. (Created by Melodee Beals, it's a series of late 18th, early 19th century cleanly transcribed newspaper articles from Scotland and Northern England; You can grab [my copy from Github](https://raw.githubusercontent.com/shawngraham/exercise/gh-pages/CND.csv)). Or perhaps you might move your copy of the Shawville equity out of DHBox onto your computer. 
3. At the command prompt in DHBox, type `$ ls` to make sure you can see your Equity folder (ie. you can't zip a folder from the command line if you are **in** that folder, so `cd` out of it if necessary). 
4. Assuming your files are in `equityfolder`, zip the folder up with this command, `$ zip -r equityfiles.zip equityfolder`. 
5. Use the filemanager to download the zip file. 
6. Unzip the folder on your machine.
7. Double-click on the file you downloaded in step 1. This will open a java-based graphical user interface with one of the most common topic-modeling approaches, 'Latent Dirichlet Allocation'.
8. Set the input to be the Colonial Newspaper Database OR the Shawville Equity folder.
9. Set the output to be somewhere neat and tidy on your computer.
10. Set the number of topics you'd like to model.
11. Click 'train topics' to run the algorithm.
12. When it finishes, go to the folder you selected for output, and find the file 'all_topics.html' in the 'output_html' folder. Click on that, and you now have a browser-based way of navigating your topics and documents. In the output_csv folder created, you will find the same information as csv, which you could then input into a spreadsheet for other kinds of visualizations (which we'll talk about in class.)

Make a note in your open notebook about your process and your observations. How does reading this material in this way change/challenge/or focus your understanding of the material?

-----

## Exercise 3: Topic Modeling in R

Exercise 2 was quite a simple way to do topic modeling. In this exercise, we are going to use a package for the R statistical language called 'Mallet' to do our topic modeling. One way isn't necessarily better than the other, although doing our analysis within R allows the potential for extending the analysis or combining it with other data. First, read [this introduction to R](../supporting materials/quick-intro-r.md) so what follows isn't a complete shock!

 - Guidance for doing this in RStudio [in the DHBox](../supporting materials/topicmodel-r-dhbox.md)
 - Guidance for doing this in RStudio [**installed on your own computer**](../supporting materials/topicmodel-r-yourmachine.md)

----

## Exercise 4: Text Analysis with Overview

In exercise 4, we're going to look at the Colonial Newspaper Database again, but this time using a tool called 'Overview'. Overview uses a different approach that the topic models we've been discussing. In essence, it looks at word frequencies and their distributions within a document, and within a corpus, to organize the documents into folders of progressively similar word use.

1. You can download Overview to run on your own machine, but for our purposes, the hosted version on the [Overview Docs website](https://www.overviewdocs.com/) is sufficient. Go to that page, watch the video, create an account, and then log in. (More help about how Overview works [may be found on their blog](https://blog.overviewdocs.com/), including helpful videos.)
2. Once you're inside, click 'import from a CSV file', and upload the CND.csv (which you can download and save to your own machine from [my Github](https://raw.githubusercontent.com/shawngraham/exercise/gh-pages/CND.csv) <- right-click and save as. 
3. On the 'UPLOAD A CSV FILE' page in Overview click 'browse' and select the CND.csv. It will give you a preview. There are a number of options here - you can tell Overview which words to ignore, and which words to give added importance to. What words will you select? Make a note in your notebook. 
4. Hit 'upload'.
5. A new page appears, called **YOUR DOCUMENT SETS**. Click on the one you just uploaded. A file folder tree showing documents of progressively greater similarity will open; on the right hand side will be the list of documents within each box (the box in question will be greyed out when you click on it, so you know where you are). You can search for words in your document, and Overview will tell you where they are; you can tag documents that you find interesting. The Overview system allows you to jump between a distant, macroscopic view and a close, document level view. 
6. Jump back and forth, see what you can find. For suggestions about how to use Overview effectively, try [their blog](https://blog.overviewdocs.com/). Make notes about what you observe in your notebook. Also, you can export your tagged document set from Overview, so that you could visualize the patterns of tagging in a spreadsheet (for instance).

**Going further:** Do you see how you could upload your documents that you collected during Module 2?

----

## Exercise 5
### Corpus Linguistics with AntConc
Heather Froelich has put together an excellent step-by-step with using AntConc for exploring textual patterns within, and across, corpora of texts. Work your way through her [tutorial](http://hfroehli.ch/workshops/getting-started-with-antconc/)

Can you get our example materials (from the Colonial Newspaper Database) into AntConc? [This might help you](http://www.themacroscope.org/?page_id=418) to split the csv into individual txt files. Alternatively, do you have any materials of your own, already collected? Feed them into AntConc. What patterns do you see? What if you compare your materials against other corpora of texts?

FYI, [here is a collection of corpora that you can explore](http://www.helsinki.fi/varieng/CoRD/corpora/index.html)

-----

## Exercise 6: Text Analysis with Voyant

In module 2 if you recall, we worked through how to transform XML using stylesheets. Melodee Beals used a [stylesheet ](https://github.com/mhbeals/Colonial-Newspaper-Database/tree/master/Transformers) to transform her database into a series of individual txt files. In the exercises above, a transformer was used to make the database into a single CSV file. In this exercise, we are going to use [Voyant Tools](http://voyant-tools.org) to visualize patterns in word use in the database. Voyant can read either a CSV *or* text files. The advantage of uploading a folder of text files is that, if the files are in chronological order, Voyant's default visualizations will also be arranged in chronological order and thus we can see change over time.

1\. Go to [Voyant Tools](http://voyant-tools.org). Paste the URL to the csv of the CND database: [https://raw.githubusercontent.com/shawngraham/exercise/gh-pages/CND.csv]([https://raw.githubusercontent.com/shawngraham/exercise/gh-pages/CND.csv]).

2\. Now, open a new browser window, and go to this [colonial newspaper file on Voyant tools](http://voyant-tools.org/?corpus=colonial-newspapers&stopList=stop.en.taporware.txt)

Do you see the difference? In the latter window, the individual articles have been uploaded individually, and thus are treated as individual documents in chronological order.

3\. Explore the corpus, comparing terms over time, looking at keywords in context, and using the RezoViz tool to create a graph where people, places, and organizations that appear in the same documents (and across documents) are connected (you can find 'rezoviz' under the cogwheel icon at the top right of the panel). Google these terms and tools for what they mean and how others have used them. You can embed any of the tools in your blogs by using the 'save' icon and getting the iframe or embed code. You can apply **stopwords** by clicking on the cogwheel in any of the different tools, and selecting stopwords. Apply the stopwords globally, and you'll only have to do this once! What patterns do you see? What do different tools highlight? Which ones are useful? What patterns do you see that strike you as interesting? Note this all down.

**Going further:** Upload materials you collected in module 2 and explore them.

-----

## Exercise 7: RAW
### Quick Charts Using RAW

A quick chart can be a handy thing to have. Google spreadsheets, Microsoft Excel, and a host of other programs can make excellent charts quickly with their wizard functions. Never hesitate to turn to these. However, they are not always good with non-numeric data. In module 3, you used the NER to extract place names from a text. After some further munging with regex, you might have ended up with a CSV that looks like [this file](https://raw.githubusercontent.com/hist3907b-winter2015/module4-holes/master/texas.csv). Can we do a quick visualization of this information? One useful tool is [RAW](http://raw.densitydesign.org/). 

1. Open RAW in a new window
2. Copy the table of data of places mentioned in the Texan correspondence, and paste it into the data input box at the top of the RAW screen.

**oh noes an error!**

#### A quick data munge
You should get an error message, to the effect that you need to check 'line 2'. What's gone wrong? RAW has checked the number of values you have in that row, and compared it to the number of columns in row 1 (which contains all the column names). It sees that the two don't match. What we need to do is add a default null value in those cells.

1\. Go to [Google Sheets](https://www.google.ca/sheets/about/)

2\. Click the 'go to google sheets' button, and then click on the big green plus sign to start a new sheet. 

3\. Paste the following into the top-left cell (cell A1):

`=IMPORTDATA("https://raw.githubusercontent.com/hist3907b-winter2015/module4-holes/master/texas.csv")`

Pretty neat, eh? Now, here's the thing: even though your sheet **looks** like it is filled with information, it's not (at least, as far as the script we are about to run is concerned). That is to say, the sheet itself only has one cell of data, and that one cell is grabbing info from elsewhere on the web and dynamically filling the sheet. The script we're going to run works only on static values (more or less).

4\. Place your cursor in cell B1. On a Mac, hit `shift+cmnd+downarrow`. On a Windows machine, hit `shift+ctrl+downarrow`. Then on Mac `shift+cmnd+rightarrow`, on Windows `shift+ctrl+rightarrow`.

5\. Copy all of that data (`cmnd+c` or `ctrl+c`).

6\. Under 'Edit' select 'paste special' -> 'paste VALUES only'.

The formula you put in cell A1 now says `#REF!`. You can delete this now. This mucking about is necessary so that the add on script we are about to run will work.

7\. We now need to fill those empty values. In the tool bar, click `add ons` -> `get add ons`. Search for `blanks`. You want to add `Blank Detector`.

8\. Now, click somewhere in your data. On Mac, hit `cmnd+a`. On Windows, hit `ctrl+a`. This highlights all of your data. 

9\. Click `Add ons` -> `blank detector` -> `detect cells`. A dialogue panel will open on the right hand side of your screen. 

10\. Click the button beside `set value` and type in `null`. 

11\. Hit `run`. All of the blank cells will fill with the word `null`. 

12\. Delete column A (which formerly had record numbers, but is now just filled with the word `null`. We don't need it). **If you get the error, 'run exceeded maximum time'** just hit the run button again. This script might take a few minutes.

You can now copy and paste your table of data into the data input box in RAW, and you should get the green thumbs up saying x records have been successfully parsed!

#### Playing with RAW
RAW takes your data, and depending on your choices, passes it into chart templates built on the d3.js code library. D3.js is a powerful library for making all sorts of charts (including interactive ones). If this sort of thing interests you, you can follow the tutorials in [Elijah Meeks' excellent new book](http://manning.com/meeks/).

1\. With your data pasted in, you can now experiment with a number of different visualizations that are all built on the d3.js code library.  
2\. Try the ‘alluvial’ diagram.  Pick place1 and place2 as your dimensions - you click and drag the green boxes under 'map your data' into the 'steps' box. 
3\. Leave the 'size' box empty. 
4\. Under 'customize your visualization' you can click inside the 'width' box to make the diagram wider and more legible.

Does anything jump out? 

5\. Try place3 and place 4. Try place1, place2, place3, and place4 in a single alluvial diagram. 

When we look at the original letters, we see that the writer often identified the town in which he was writing, and the town of the addressee. Why choose the third and fourth places? Perhaps it makes sense, for a given research question, to assume that with the pleasantries out of the way the writers will discuss the places important to their message. Experiment! This is one of the joys of working with data, experimenting to see how you can deform your materials to see them in a new light.

6\. You can export your visualization under the 'download' box at the bottom of the RAW page - your choices are as a simple raster image (png), a vector image (svg) or a data representation (json).

-----
## Exercise 8: Simple Mapping and Georectifying

In this exercise, you will find a historical map online, upload a copy to a mapwarper service, georectify it, and then display the map online, via a hosted service like CartoDB, and also through a map you will build yourself using leaflet.js. Finally, we will also convert csv to geojson using http://togeojson.com/, and we'll map that as a github gist. We'll also grab a geojson file hosted on github gist and import it into cartodb.

### Georectifying
Georectifying is the process of taking an image (whether it is of a historical map, chart, airphoto, or whatever) and manipulating its geometry so that it matches a geographic projection. Think of it like this: you take your handdrawn map, and use pushpins to pin down known locations on your map to a globe. As you pin, your image stretches and warps. Traditionally, this has not been an easy thing to do, if you are new to GIS. In recent years, the curve has flattened significantly. In this exercise, we'll grab an image, upload it to the Harvard Library MapWarper service, and then export it as a tileset which can be used in other mapping programs.

1. Get a historical map. I like the Fire Insurance plans from the [Gatineau Valley Historical Society](http://www.gvhs.ca/research/maps-fire-insurance.html); I'm sure you can find others to suit your interests.
2. Right-click, save as.... grab a copy. Save it somewhere handy.
3. Go to [Harvard World MapWarp](http://warp.worldmap.harvard.edu/) and sign up for an account. Then login.
4. Go to the upload screen: <br> ![Image showing upload screen for Harvard World Maps](http://i.imgur.com/bmNCzg6.png)
5. Fill in as much of the metadata as you can. Then select your map from your computer, and upload it.
6. On the next page, click 'rectify'. <br> ![Image showing user ability to rectify the historical map on the left with the modern map on the right to ensure locations match coordinates](http://i.imgur.com/yULDRQR.jpg)
7. Pan and zoom both maps until you're sure you're looking at the same area in both. Double click in a map, select the pencil icon, and click on a point (location) you are sure you can match in the other window. Then click on the other map window, select the pencil, and then click on the same point. The 'add control point' button below and between both maps will light up. Click on this to confirm that this is a control point you want. Do this at least three times; the more times you can do it, the better the map warp.
8. Having selected your control points, click on 'warp image'.
9. You can now click on the 'export' panel, and get the URL for your georectified image in a few different formats. If you clicked on the KML option, a google map window will open [like so](https://maps.google.com/maps?q=http://warp.worldmap.harvard.edu/maps/4152.kml&output=classic&dg=feature). For many webmapping applications, the Tiles (Google/OSM scheme): Tiles Based URL is what you want. You'll get a URL like this: ```http://warp.worldmap.harvard.edu/maps/tile/4152/z/x/y.png```   Save that info. You'll need it later.

You have now georectified a map. Let's use that map as a base layer in [Palladio](http://palladio.designhumanities.org/#/)

We need some place data for Palladio. Here's what I'm using <br> ![Image for Palladio showing coordinates of landmarks in Ottawa](http://i.imgur.com/vTEiRxh.png) <br> Note how I've formatted this data. I'll be copying and pasting it into Palladio. (For more on how to input geographic data into Palladio, see [this tutorial](http://hdlab.stanford.edu/doc/scenario-point-to-point.pdf)). Basically, you want something like this:<br>

|   | Place      | Coordinates            |
|---|------------|------------------------|
|   | Mexico     | 23.634501,-102.552784  |
|   | California | 36.778261,-119.4179324 |
|   | Brazos     | 32.661389,-98.121667   |

etc: that is, a tab between 'place' and 'coordinates' in the first line, a tab between 'mexico' and the latitude, and a comma between latitude and logitude.

10\. Go to [Palladio](http://palladio.designhumanities.org/). Hit 'start' then 'upload spreadsheet or csv'. In the box, paste in your data. **You can progress to the next step without having any real data: just paste or type something in - see the video below.** Obviously, you won't have any points on your map, but if you were having trouble with that step, this allows you to bypass it to continue on with this tutorial.
11\. Click on 'map'
12\. Under 'places', select 'coordinates'
13\. Click 'add new layer'
14\. In the popup, beside 'Choose one of Palladio default layers or create a new one.', select 'custom'. This is where you're going to paste it that tiles based URL from the map warper
15\. Paste in the URL, but **replace** the ```/z/x/y``` part with ```{z}/{x}/{y}```
16\. Click add

Here is a video walk through; places where you might have got into trouble include getting past the initial data entry box on Palladio, and finding where exactly to past in your georectified map url.

<iframe width="420" height="315" src="https://www.youtube.com/embed/KgLrvcA8v_M" frameborder="0" allowfullscreen></iframe>

Congratulations! You've georectified a map, and used it as a base layer for a visualization of some point data. References these [notes on using a georectified map with the CartoDB service](https://gist.github.com/shawngraham/a49a9834984ae0792345).

![Image showing historical map overlayed on modern map](http://i.imgur.com/0gCjh5X.jpg)

----

## Exercise 9: Network Analysis in R

Earlier, we took the index from the Texan Correspondence, a list of letters from so-and-so to so-and-so. When we stitch that together into a network of people connected because they exchanged letters, we end up with a shard of their social network. Networks can be queried for things like power, position, and role, and so used judiciously, we can begin to suss something of the social structures in which their history took place.Before you go any further, make sure you also take a long look at Scott Weingart's series, [Networks Demystified](http://scottbot.net/HIAL/?s=%20networks%20demystified). Finally, [heed our warning](http://www.themacroscope.org/?page_id=449).

This exercise uses the R language to do our analysis, which in DHBox we access via R Studio, a programming environment. Please read [the introduction to R in our supporting materials](../supporting materials/quick-intro-r.md) and then progress to the [exercise](../supporting materials/netviz.md).

## Exercise 10: QGIS
### QGIS

There are many excellent tutorials around concerning how to get started with GIS. Our own library, in the [MADGIC centre](https://www.library.carleton.ca/contact/service-points/maps-data-and-government-information-centre) has tremendous resources and I would encourage you to speak with the map librarians before embarking on any *serious* mapping projects. In the short term, the historian [Fred Gibbs](http://fredgibbs.net/) has an excellent series on using the open source GIS platform *QGIS* to make and map historical data.

For this exercise, I would recommend you try Gibbs' first tutorial,

['Making a map with QGIS'](http://fredgibbs.net/tutorials/qgis/making-a-map-with-qgis.html)

...and then, try georectifying a historical map and adding it to your GIS:

['Using Historical maps with qgis'](http://fredgibbs.net/tutorials/qgis/overlaying-historic-maps-with-qgis.html)

## Going Further
There are many tutorials at [The Programming Historian](http://programminghistorian.org/lessons/) that are appropriate here. Try some under the 'data manipulation' or 'distant reading' headings.
