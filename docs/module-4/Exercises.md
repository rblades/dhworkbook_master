# Module 4 Exercises

There are **many** [different tools and approaches](http://dhresourcesforprojectbuilding.pbworks.com/w/page/69244314/Tutorials%20for%20DH%20Tools%20and%20Methods) you could use to visualize your data, both as a preliminary pass to spot the holes and also for more formal analysis. In which case, for this module, I would like you to select **two** of these exercises which seem most relevant to your capstone exercise.

You are welcome to work through more of them, of course, but I want the exercises to move your own research forward. Some of these I wrote and some are adapted from [The Macroscope](http://themacroscope.org); others are adapted or used holus-bolus from scholars like [Miriam Posner](http://miriamposner.com/blog/), [Fred Gibbs](http://fredgibbs.net/), and [Heather Froehlich](http://hfroehli.ch/) (and I'm grateful that they shared their materials!). Finally, you are welcome to explore the lessons and tutorials at [The Programming Historian](http://programminghistorian.org/lessons/) if they seem appropriate to what you want to do for the Capstone Exercise.

**But what if I haven't any idea of what to do for the capstone exercise?** Then read through the various tutorials for inspiration. Find something that strikes you as interesting, and then talk to me about how you might employ the ideas or concepts with regard to the Canadian war diary data.

## Things to install?

Many of these involve having to install more software on your own machine. In those exercises that involve using R and RStudio, you are welcome to install RStudio on your own machine OR to use it in DH Box. Please read [this quick introduction to R and Rstudio carefully](../supporting materials/quick-intro-r.md).

**If you decide to install R and RStudio on your own machine,** I would suggest you read the introductory bits from Lincoln Mullen's book-in-progress, [Computational Historical Thinking](http://dh-r.lincolnmullen.com/getting-started.html), especially the 'setup' part under 'getting started' (pay attention to the bit on installing packages and dependencies). If you spot any exercises in Mullen's book that seem relevant to the Capstone Exercise, you may do those as an alternative to the ones here. **Alternatively**, go to [Swirl](http://swirlstats.com/) and [learn the basics of R within Swirl](http://swirlstats.com/students.html). [DHNow](http://digitalhumanitiesnow.org/2016/01/resource-basic-text-mining-in-r/) links to a new [Basic Text Mining in R](https://web.archive.org/web/20160309170928/https://rstudio-pubs-static.s3.amazonaws.com/31867_8236987cf0a8444e962ccd2aec46d9c3.html) tutorial which is worth checking out as well.

**NB It is always very important to record in your own notebooks what version of R you used for your analysis, what version of any R packages you installed and used, and so on because packages can go out of date.**

In the table below I've gathered the exercises together under the headings of **Text**, **Networks**, **Maps**, and **Charts**. I've also added some entries that I am categorizing under **Art**. The first is a series of exercises on [the sonification of data](http://programminghistorian.org/lessons/sonification) and the second is a guide [to making Twitterbots](https://programminghistorian.github.io/ph-submissions/lessons/intro-to-twitterbots); the third is about glitching digital imagery. These approaches can provide surprising and novel insights into history, as they move from representing history digitally to **performing** it. Visit, for instance, [the final project in an undergraduate digital history class at the University of Saskatchewan by Daniel Ruten](https://danielruten.wordpress.com/2017/04/15/sonic-word-clouds-an-experiment-with-data-sonification-part-i-introduction/). Daniel translated simple word clouds of a First World War diary into a profound auditory performance. I would be very interested indeed to see if any capstone exercises in HIST3814o gave sonification or Twitterbots or glitching a try.

The exercises in this module are covered in the chart below:

| Texts        | Networks         | Maps  | Charts | Art |
| ------------- |:-------------:|:-----:|:--------:|--------:|
| [Topic Modeling Tool](#exercise-2-topic-modeling-tool)  |[Network analysis in Gephi](#exercise-1-network-visualization) |[Simple mapping & georectifying](#exercise-8-simple-mapping-and-georectifying) |[Quick charts using RAW](#exercise-7-raw) |[Sonification](https://programminghistorian.org/lessons/sonification)|
| [Topic Modeling in R](#exercise-3-topic-modeling-in-r)  |[Network Analysis in R](#exercise-9-network-analysis-in-r) |[QGIS (tutorials by Fred Gibbs)](#exercise-10-qgis) | |[Twitterbots](https://programminghistorian.github.io/ph-submissions/lessons/intro-to-twitterbots)|
| [Text Analysis with OverviewProject](#exercise-4-text-analysis-with-overview) |[Network Analysis in Cytoscape](https://github.com/miriamposner/cytoscape_tutorials) |[Geoparsing with Python](../supporting materials/geoparsing-w-python.txt.md) | |[Glitching Photos](../supporting materials/glitch.md) |
| [Corpus Linguistics with AntConc](#exercise-5-corpus-linguistics-with-antconc)  |[Choose your own adventure](../supporting materials/cyoa.txt.md)|[Palladio with Posner](http://miriamposner.com/blog/getting-started-with-palladio/) | | |
| [Text Analysis with Voyant](#exercise-6-text-analysis-with-voyant) |[Using igraph to visualize network data](../supporting materials/netviz.md)|[Leaflet.js Maps](../supporting materials/leaflet.txt.md) | | |
| [Identifying Similar Images with TensorFlow](#exercise-11-identifying-similar-images-with-tensorflow)| | | 

----------------------

## Exercise 1: Network Visualization

This exercise uses the open source program **Gephi** which you install on your own computer. If you'd rather not install anything, please see [Network Analysis in R](#exercise-9-network-analysis-in-r) instead.

Recall that the index of the collected letters of the Republic of Texas was just a list of letters from so-and-so to so-and-so. We haven't looked at the content of those letters, but the shape of network &mdash; the meta data of that correspondence &mdash; can be revealing (remember [Paul Revere!](https://kieranhealy.org/blog/archives/2013/06/09/using-metadata-to-find-paul-revere/)) When we stitch that together into a network of people connected because they exchanged letters, we end up with a shard of their social network. Networks can be queried for things like power, position, and role, and so used judiciously, we can begin to suss something of the social structures in which their history took place. I would recommend that you also take a long look at Scott Weingart's series, [Networks Demystified](http://scottbot.net/networks-demystified-9-modality/). Finally, [heed our warning](http://www.themacroscope.org/?page_id=449).

For this exercise, do the following: 

1. Transform your Texan Correspondence data into a network, which you will then visualize with the open source program **Gephi**. The detailed instructions are [in our supporting materials](../supporting materials/gephi.txt.md).

### Going Further

The data you get from topic modeling is in many ways just the first step to making it meaningful. Read through [Miram Posner's article, **Very basic strategies for interpreting results from the Topic Modeling Tool**](http://miriamposner.com/blog/very-basic-strategies-for-interpreting-results-from-the-topic-modeling-tool/). In this article, Posner explores the results of your data, what the different files mean, and how you can interpret that data.

Posner also shows in another article [how you can visualize your results from the Topic Modeling Tool](http://miriamposner.com/classes/dh201w19/tutorials-guides/text-analysis/visualize-your-topic-model/). While visualization is just one method to interpret your data, it is a powerful way to begin to make some meaningful insights into the data.

-----

## Exercise 2: Topic Modeling Tool
In this exercise you will use the **Topic Modeling Tool** to create a simple topic model and a webpage that allows you to browse the results.

1. Download the [Topic Modeling Tool from GitHub](https://github.com/senderle/topic-modeling-tool).

2. Make sure you have some content on your own machine; the Colonial Newspaper Database is a handy corpus. (Created by Melodee Beals, it's a series of late 18th, early 19th century cleanly transcribed newspaper articles from Scotland and Northern England; You can grab [my copy from GitHub](https://raw.githubusercontent.com/shawngraham/exercise/gh-pages/CND.csv)). Or perhaps you might move your copy of the Canadian war diary out of DH Box onto your computer. 

3. At the command prompt in DH Box, type `$ ls` to make sure you can see your Canadian war diary text folder (ie. you can't zip a folder from the command line if you are **in** that folder, so `$ cd` out of it if necessary). 

4. Assuming your files are in `war-diary-text`, zip the folder up with this command, `$ zip -r wardiaryfiles.zip war-diary-text`. 

5. Use the File Manager to download the zip file. 

6. Unzip the folder on your machine.

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/uwkI6M3wLCY?rel=0" title="Installing and preparing data for the Topic Modeling Tool" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br> 

7. Double-click on the file you downloaded in Step 1. This will open a java-based graphical user interface with one of the most common topic modeling approaches, 'Latent Dirichlet Allocation'.

8. Set the input to be the Colonial Newspaper Database **or** the Canadian war diary.

9. Set the output to be somewhere neat and tidy on your computer.

10. Set the number of topics you'd like to model.

11. Click 'train topics' to run the algorithm.

12. When it finishes, go to the folder you selected for output, and find the file `all_topics.html` in the `output_html` folder. 

13. Click on `all_topics.html`. You now have a browser-based way of navigating your topics and documents. In the `output_csv` folder created, you will find the same information as CSV, which you could then input into a spreadsheet for other kinds of visualizations (which we'll talk about in class).

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/mFvSBR9mze8?rel=0" title="Viewing the topic model files" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br> 

Make a note in your open notebook about your process and your observations. How does reading this material in this way change/challenge/or focus your understanding of the material?

-----

## Exercise 3: Topic Modeling in R

Exercise 2 was quite a simple way to do topic modeling. In this exercise, we are going to use a package for the R statistical language called 'Mallet' to do our topic modeling. One way isn't necessarily better than the other, although doing our analysis within R allows the potential for extending the analysis or combining it with other data. First, read [this introduction to R](../supporting materials/quick-intro-r.md) so what follows isn't a complete shock!

For this exercise, do **ONE** of the following: 

1. Guidance for doing this in RStudio [**in the DH Box**](../supporting materials/topicmodel-r-dhbox.md)
2. Guidance for doing this in RStudio [**installed on your own computer**](../supporting materials/topicmodel-r-yourmachine.md)

-----

## Exercise 4: Text Analysis with Overview

In this exercise, we're going to look at the Colonial Newspaper Database again, but this time using a tool called 'Overview'. Overview uses a different approach than the topic models we've been discussing. In essence, it looks at word frequencies and their distributions within a document, and within a corpus, to organize the documents into folders of progressively similar word use.

1. You can download Overview to run on your own machine, but for our purposes, the hosted version on the [Overview Docs website](https://www.overviewdocs.com/) is sufficient. Go to that page, watch the video, create an account, and then log in (**you must create an account to use Overview**). (More help about how Overview works [may be found on their blog](https://blog.overviewdocs.com/), including helpful videos.)
2. Once you're inside, click 'import from a CSV file', and upload the `CND.csv` (which you can download and save to your own machine from [my GitHub](https://raw.githubusercontent.com/shawngraham/exercise/gh-pages/CND.csv) <- right-click and save as the previous link). 
3. On the 'UPLOAD A CSV FILE' page in Overview click 'browse' and select the `CND.csv`. It will give you a preview. There are a number of options here &mdash; you can tell Overview which words to ignore, and which words to give added importance to. What words will you select? Make a note in your notebook. 
4. Hit 'upload'.
5. A new page appears, called **YOUR DOCUMENT SETS**. Click on the one you just uploaded. A file folder tree showing documents of progressively greater similarity will open; on the right side will be the list of documents within each box (the box in question will be greyed out when you click on it, so you know where you are). You can search for words in your document, and Overview will tell you where they are; you can tag documents that you find interesting. The Overview system allows you to jump between a distant, macroscopic view and a close, document level view. 
6. Jump back and forth, see what you can find. For suggestions about how to use Overview effectively, try [their blog](https://blog.overviewdocs.com/). Make notes about what you observe in your notebook. Also, you can export your tagged document set from Overview, so that you could visualize the patterns of tagging in a spreadsheet (for instance).

<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/1KSQcATewcY?rel=0" title="Analyising text with Overview" frameborder="0" gesture="media" allowfullscreen></iframe>
<br> 

**Going further:** Do you see how you could upload your documents that you collected during Module 2?

-----

## Exercise 5: Corpus Linguistics with AntConc

Heather Froelich has put together an excellent step-by-step with using AntConc for exploring textual patterns within, and across, corpora of texts. Work your way through her [tutorial](http://hfroehli.ch/workshops/getting-started-with-antconc/).

Can you get our example materials (from the Colonial Newspaper Database) into AntConc? [Our instructions in The Macroscope](http://www.themacroscope.org/?page_id=418) might help you to split the CSV into individual txt files. Alternatively, do you have any materials of your own, already collected? Feed them into AntConc. What patterns do you see? What if you compare your materials against other corpora of texts?

For your information, [CoRD has a collection of corpora that you can explore](http://www.helsinki.fi/varieng/CoRD/corpora/index.html).

-----

## Exercise 6: Text Analysis with Voyant

In [Module 2](../module-2/Exercises/#exercise-3-tei), if you recall, we worked through how to transform XML using stylesheets. Melodee Beals used a [stylesheet ](https://github.com/mhbeals/Colonial-Newspaper-Database/tree/master/Transformers) to transform her database into a series of individual txt files. In the exercises above, a transformer was used to make the database into a single CSV file. In this exercise, we are going to use [Voyant Tools](http://voyant-tools.org) to visualize patterns of word use in the database. Voyant can read either a CSV **or** text files. The advantage of uploading a folder of text files is that, if the files are in chronological order, Voyant's default visualizations will also be arranged in chronological order and thus we can see change over time.

1. Go to [Voyant Tools](http://voyant-tools.org). Paste the following URL to the CSV of the CND database: [https://raw.githubusercontent.com/shawngraham/exercise/gh-pages/CND.csv](https://raw.githubusercontent.com/shawngraham/exercise/gh-pages/CND.csv).

2. Now, open a new browser window, and go to the [colonial newspaper file on Voyant tools](http://voyant-tools.org/?corpus=colonial-newspapers&stopList=stop.en.taporware.txt).

    Do you see the difference? In the latter window, the individual articles have been uploaded individually, and thus are treated as individual documents in chronological order.

3. Explore the corpus, comparing terms over time, looking at keywords in context, and using the RezoViz tool to create a graph where people, places, and organizations that appear in the same documents (and across documents) are connected (you can find 'rezoviz' under the cogwheel icon at the top right of the panel). 

4. Google these terms and tools for what they mean and how others have used them. You can embed any of the tools in your blogs by using the 'save' icon and getting the iframe or embed code. You can apply **stopwords** by clicking on the cogwheel in any of the different tools, and selecting stopwords. 

5. Apply the stopwords globally, and you'll only have to do this once! What patterns do you see? What do different tools highlight? Which ones are useful? What patterns do you see that strike you as interesting? Note this all down.

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/mQJt_M8KyHU?rel=0" title="Analyising text with Voyant" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br> 

**Going further:** Upload materials you collected in Module 2 and explore them.

-----

## Exercise 7: RAW
### Quick Charts Using RAW

A quick chart can be a handy thing to have. Google spreadsheets, Microsoft Excel, and a host of other programs can make excellent charts quickly with their wizard functions. Never hesitate to turn to these. However, they are not always good with non-numeric data. In [Module 3](../module-3/Exercises/#going-further), you used the Stanford Named Entity Recognizer to extract place names from a text. After some further munging with regex, you might have ended up with a CSV that looks like [the Texas CSV](https://raw.githubusercontent.com/hist3907b-winter2015/module4-holes/master/texas.csv). Can we do a quick visualization of this information? One useful tool is [RAW](http://app.rawgraphs.io/). 

1. Open RAW in a new window.
2. Copy the table of data of places mentioned in the Texan correspondence, and paste it into the data input box at the top of the RAW screen.

**Oh no, an error!**

#### A quick data munge
You should get an error message, to the effect that you need to check 'line 2'. What's gone wrong? RAW has checked the number of values you have in that row, and compared it to the number of columns in row 1 (which contains all the column names). It sees that the two don't match. What we need to do is add a default null value in those cells.

1. Go to [Google Sheets](https://www.google.ca/sheets/about/).

2. Click the 'Go to Google Sheets' button, and then click on the big green plus sign to start a new sheet. 

3. Paste the following into the top-left cell (cell A1):

        =IMPORTDATA("https://raw.githubusercontent.com/hist3907b-winter2015/module4-holes/master/texas.csv")

    Pretty neat, eh? Now, here's the thing: even though your sheet **looks** like it is filled with information, it's not (at least, as far as the script we are about to run is concerned). That is to say, the sheet itself only has one cell of data, and that one cell is grabbing info from elsewhere on the web and dynamically filling the sheet. The script we're going to run works only on static values (more or less).

4. Place your cursor in cell B1. On a Mac, hit `shift+cmnd+downarrow`. On a Windows machine, hit `shift+ctrl+downarrow`. Then on Mac `shift+cmnd+rightarrow`, on Windows `shift+ctrl+rightarrow`.

5. Copy all of that data (`cmnd+c` or `ctrl+c`).

6. Under 'Edit' select 'paste special' -> 'paste VALUES only'.

    The formula you put in cell A1 now says `#REF!`. You can delete this now. This mucking about is necessary so that the add on script we are about to run will work.

7. We now need to fill those empty values. In the tool bar, click `add ons` -> `get add ons`. Search for `blanks`. You want to add `Blank Detector`.

8. Now, click somewhere in your data. On Mac, hit `cmnd+a`. On Windows, hit `ctrl+a`. This highlights all of your data. 

9. Click `Add ons` -> `blank detector` -> `detect cells`. A dialogue panel will open on the right side of your screen. 

10. Click the button beside `set value` and type in `null`. 

11. Hit `run`. All of the blank cells will fill with the word `null`. 

12. Delete column A (which formerly had record numbers, but is now just filled with the word `null`. We don't need it). **If you get the error, 'run exceeded maximum time'** just hit the run button again. This script might take a few minutes.

    You can now copy and paste your table of data into the data input box in RAW, and you should get the green thumbs up saying 'x records have been successfully parsed!'

    **NB The Blank Detector add on may take a long time. Try it out on the CSV. You can copy the parsed data from [my Google Sheets file](https://docs.google.com/spreadsheets/d/12FRAMe0QaDfii3JL4RS7XYHiOFMusUVHhGsfP79uYaE/edit?usp=sharing).**

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/FmvH-9nP4AM?rel=0" title="Importing data into RAW" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br> 

#### Playing with RAW
RAW takes your data, and depending on your choices, passes it into chart templates built on the [D3.js](https://d3js.org/) code library. D3.js is a powerful library for making all sorts of charts (including interactive ones). If this sort of thing interests you, you can follow the tutorials in [Elijah Meeks' excellent new book](http://manning.com/meeks/).

1. With your data pasted in, you can now experiment with a number of different visualizations that are all built on the D3.js code library.  

2. Try the ‘alluvial’ diagram.  Pick place1 and place2 as your dimensions &mdash; you click and drag the green boxes under 'map your data' into the 'steps' box. 

3. Leave the 'size' box empty. 

4. Under 'customize your visualization' you can click inside the 'width' box to make the diagram wider and more legible.

    Does anything jump out? 

5. Try place3 and place 4. Try place1, place2, place3, and place4 in a single alluvial diagram. 

    When we look at the original letters, we see that the writer often identified the town in which he was writing, and the town of the addressee. Why choose the third and fourth places? Perhaps it makes sense, for a given research question, to assume that with the pleasantries out of the way the writers will discuss the places important to their message. Experiment! This is one of the joys of working with data, experimenting to see how you can deform your materials to see them in a new light.

6. You can export your visualization under the 'download' box at the bottom of the RAW page &mdash; your choices are as a simple raster image (PNG), a vector image (SVG) or a data representation (json).

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/jcDLQxeTjDo?rel=0" title="Playing with RAW" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

-----

## Exercise 8: Simple Mapping and Georectifying

In this exercise, you will find a historical map online, upload a copy to a map warper service, georectify it, and then display the map online, via a hosted service like CartoDB, and also through a map you will build yourself using Leaflet.js. Finally, we will also convert CSV to geojson using [Mapbox's geojson converter](https://mapbox.github.io/togeojson/), and we'll map that as a GitHub gist. We'll also grab a geojson file hosted on GitHub gist and import it into cartodb.

### Georectifying
Georectifying is the process of taking an image (whether it is of a historical map, chart, airphoto, or whatever) and manipulating its geometry so that it matches a geographic projection. Think of it like this: you take your handdrawn map, and use pushpins to pin down known locations on your map to a globe. As you pin, your image stretches and warps. Traditionally, this has not been an easy thing to do, if you are new to GIS. In recent years, the curve has flattened significantly. In this exercise, we'll grab an image, upload it to the Map Warper website, and then export it as a tileset which can be used in other mapping programs.

1. Get a historical map. I like the Fire Insurance plans from the [Gatineau Valley Historical Society](http://www.gvhs.ca/research/maps/maps-fire-insurance.html); I'm sure you can find others to suit your interests.

2. Right-click and save as to grab a copy. Save it somewhere easily accessible.

3. Go to [Map Warper](http://mapwarper.net) and sign up for an account. Then login.

4. Go to the upload screen: <br> ![Image showing upload screen for Map Warper](http://i.imgur.com/bmNCzg6.png)

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/jCTPKf1T4Wo?rel=0" title="Getting a historical map" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

5. Fill in as much of the metadata as you can. Then select your map from your computer, and upload it.

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/GGlDkEwRj8g?rel=0" title="Adding metadata to your map" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

6. On the next page, click 'Rectify'. <br> ![Image showing user ability to rectify the historical map on the left with the modern map on the right to ensure locations match coordinates](http://i.imgur.com/yULDRQR.jpg)

7. Pan and zoom both maps until you're sure you're looking at the same area in both. Double click in a map, select the location icon, and click on a point (location) you are sure you can match in the other window.

8. Click on the other map window, select the location icon, and then click on the same point. 

9. Note the 'Add control point' button below and between both maps will light up. Click on this to confirm that this is a control point you want. Do this at least three times; the more times you can do it, the better the map warp.

10. Having selected your control points, click on 'Warp image'.

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/nhKvIGEDR9I?rel=0" title="Georectifying your map" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

11. You can now click on the 'Export' panel, and get the URL for your georectified image in a few different formats. If you clicked on the KML option, a new Google Map window will open. For many web mapping applications, the Tiles (Google/OSM scheme): Tiles Based URL is what you want. You'll get a URL like this: ```http://mapwarper.net/maps/tile/27421/{z}/{x}/{y}.png```. Save that info. You'll need it later.

    You have now georectified a map. Let's use that map as a base layer in [Palladio](http://palladio.designhumanities.org/#/).

12. Go to [Palladio](http://palladio.designhumanities.org/). Hit 'start'. You will see 'Load .csv or spreadsheet'. 

13. In the box, paste in some data. **You can progress to the next step without having any real data: just paste or type something in and hit enter so you have two lines.** Obviously, you won't have any points on your map, but if you were having trouble with that step, this allows you to bypass it to continue on with this tutorial.

14. Click the 'Map' tab at the top of the screen.

15. Click 'New layer' on the right side menu.

16. Click the Tiles tab in the right side menu.

17. Select Custom Tiles.

18. Paste your Map Warper URL into the Tileset URL field. Your URL will look like `http://mapwarper.net/maps/tile/27421/{z}/{x}/{y}.png`.

19. Click 'Add layer'.

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/-9UEgWQIM2o?rel=0" title="Importing your map into Palladio" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

Congratulations! You've georectified a map, and used it as a base layer for a visualization of some point data. Reference [these notes on using a georectified map with the CartoDB service](https://gist.github.com/shawngraham/a49a9834984ae0792345).

![Image showing historical map overlayed on modern map](http://i.imgur.com/0gCjh5X.jpg)

-----

## Exercise 9: Network Analysis in R

Earlier, we took the index from the Texan Correspondence, a list of letters from so-and-so to so-and-so. When we stitch that together into a network of people connected because they exchanged letters, we end up with a shard of their social network. Networks can be queried for things like power, position, and role, and so used judiciously, we can begin to suss something of the social structures in which their history took place. Before you go any further, make sure you also take a long look at Scott Weingart's series, [Networks Demystified](http://scottbot.net/networks-demystified-9-modality/). Finally, [heed our warning](http://www.themacroscope.org/?page_id=449).

This exercise uses the R language to do our analysis, which in DH Box we access via RStudio, a programming environment. 

For this exercise, do the following: 

1. Please read [the introduction to R in our supporting materials](../supporting materials/quick-intro-r.md).
2. Then progress to the [netviz exercise](../supporting materials/netviz.md).

-----

## Exercise 10: QGIS

There are many excellent tutorials around concerning how to get started with GIS. Our own MacOdrum Library's [MADGIC centre](https://www.library.carleton.ca/contact/service-points/maps-data-and-government-information-centre) has tremendous resources and I would encourage you to speak with the map librarians before embarking on any **serious** mapping projects. In the short term, the historian [Fred Gibbs](http://fredgibbs.net/) has an excellent series on using the open source GIS platform **QGIS** to make and map historical data.

For this exercise, do the following: 

1. Try Gibbs' first tutorial, ['Making a map with QGIS'](http://fredgibbs.net/tutorials/qgis/making-a-map-with-qgis.html).

    Installing QGIS

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/Ak6O5I1cqiQ?rel=0" title="Installing QGIS" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

    Downloading geographic data

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/h7vVOVpuzR8?rel=0" title="Downloading geographic data" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

    Displaying data in QGIS

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/6620y9_r-80?rel=0" title="Displaying data in QGIS" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

2. Next, try georectifying a historical map and adding it to your GIS following Gibbs' other tutorial ['Using Historical maps with QGIS'](http://fredgibbs.net/tutorials/qgis/overlaying-historic-maps-with-qgis.html).

-----

## Exercise 11: Identifying Similar Images with TensorFlow

This exercise uses uses a [jupyter notebook](https://jupyter.org/) to run the code. You can launch this jupyter notebook in an executable environment by clicking on the button below.

[![Binder](https://mybinder.org/badge.svg)](http://mybinder.org/v2/gh/shawngraham/bindr-test-Identifying-Similar-Images-with-TensorFlow/master)

This exercise is based on Douglas Duhaime's tutorial [identifying similar images with tensorflow](http://douglasduhaime.com/posts/identifying-similar-images-with-tensorflow.html) which is very clearly laid out and explained. In this notebook, I've compressed the steps. The 'images' directory only has 25 images in it for demo purposes. In Duhaime's post, the images folder (that you grab with `wget` has about 2000 images in it).

1. Launch the [jupyter notebook](http://mybinder.org/v2/gh/shawngraham/bindr-test-Identifying-Similar-Images-with-TensorFlow/master). This may take up to a minute to finish loading.
2. Open the `find-similar-images.ipynb` file. You'll notice that the notebook is already pre-populated with commands.
3. For each section, click the button labelled `|> Run`. This will either skip to the next paragraph if it is text/information or run the command if it is a command. Each time the run finishes, check the main notebook with the file listings. The notebook will update and create new files as different commands run.
4. Click `|> Run` through each command/section.
5. Open the `Affinity Propagation.ipynb` file and for each section, click the button labelled `|> Run`. Notice the clusters that are created.

### Going Further

Now that you understand the basics of the TensorFlow exercise, try running your own jupyter instance.

1. Navigate to Dr. Graham's [TensorFlow GitHub respository](https://github.com/shawngraham/Identifying-Similar-Images-with-TensorFlow-notebooks).
2. Fork the repository so you have your own version. 
3. Drop more images into the image folder.
5. Navigate to the [Binder website](https://mybinder.org/).
6. Paste the URL of your forked GitHub repository into the section labelled `GitHub repository name or URL`.
7. Click the button labelled `launch` to create your own instance of the jupyter notebook.
8. When the Binder finishes building, click the text labelled `Copy the text below, then paste into your README to show a binder badge: launch|Binder    >`.
9. Copy the Markdown link to your Binder instance.
9. Navigate to your forked repository on GitHub.
10. Open the `README.md` file and click the pen/pencil icon to edit the file.
11. Use the button text you copied in step 8 to change the link for the button labelled `launch|Binder` from the link to Dr. Graham's Binder instance to your new Binder URL, otherwise clicking the button in your GitHub repository will just open Dr. Graham's original repository. 

-----

## Going Further
There are many tutorials at [The Programming Historian](http://programminghistorian.org/lessons/) that are appropriate here. Try some under the 'Data Manipulation' or 'Distant Reading' headings.

