# Working with Gephi

**Before we go much further, I would recommend that you look at the work of Clement Levallois, who has a [suite of excellent tutorials on working with Gephi](https://seinecle.github.io/gephi-tutorials/). The tutorial below is adapted from our open draft of [The Macroscope](http://themacroscope.org).**

## Introduction
Gephi is quickly becoming the tool of choice for network analysts who do not need the full suite of algorithms offered by [Pajek](http://vlado.fmf.uni-lj.si/pub/networks/pajek/) or [UCINET](https://sites.google.com/site/ucinetsoftware/home). It is relatively easy to use (eclipsed in this only by [NodeXL](http://nodexl.codeplex.com/)), it is usable on all platforms, it can analyze fairly large networks, and it creates beautiful visualizations. The development community is also extremely active, with improvements being added constantly. We recommend Gephi for the majority of historians undertaking serious network analysis research. 

Download and install [Gephi](http://gephi.github.io) onto your machine. 

### Installing Gephi on OS 10 Mavericks

**NB Since writing this, Gephi announced the [release of Gephi 0.9](https://gephi.wordpress.com/2015/12/21/gephi-0-9-released-play-with-network-data-again/). This newer Gephi should solve these problems.**

Mac users might have some trouble installing Gephi 0.8. We have found that, on Mac OS X Mavericks, Gephi does not load properly after installation. This is a Java-related issue, so you’ll need to install an earlier version of Java than the one provided. 

To fix this:

1\. Control click (or right-click) on the Gephi package

2\. Select “show package contents.” 

3\. Click on “contents >> resources >> gephi >> etc.” 

4\. Control-click (or right-click) on “gephi.conf” and open with your text editor. 

5\. Find the line reading:

```#jdkhome="/path/to/jdk"```

and paste the following code:

``` 
jdkhome="/System/Library/Java/JavaVirtualMachines/1.6.0.jdk/Contents/Home 
```

6\. Save that file. Then, go to [Apple support](http://support.apple.com/kb/DL1572) and install the older version of Java (Java 6). Once that is installed, Gephi should run normally.

7\. Run Gephi once it is installed. You will be presented with a welcome prompting you to open a recent file, create a new project, or load a sample file. 

8\. Click “New Project” and then click the “Data Laboratory” tab on the horizontal bar at the top of the Gephi window (Fig. 7.3).

## When Not To Use Networks 

Networks analysis can be a powerful method for engaging with a historical dataset but it is often not the most appropriate. Any historical database may be represented as a network with enough contriving but few should be. One could take the Atlantic trade network, including cities, ships, relevant governments and corporations, and connect them all together in a giant multipartite network. It would be extremely difficult to derive any meaning from this network, especially using traditional network analysis methodologies. Clustering coefficients (a useful network metric), for example, would be meaningless in this situation, as it would be impossible for the neighbors of any one node to be neighbors with one another. Network scientists have developed algorithms for [multimodal networks](http://www.scottbot.net/HIAL/?p=41158), but they are often created for fairly specific purposes, and one should be very careful before applying them to a different dataset and using that analysis to explore a historiographical question.

Networks, as they are commonly encoded, also suffer from a profound lack of nuance. It is all well to say that, because Henry Oldenburg corresponded with both Gottfried Leibniz and John Milton, he was the short connection between the two men. However, the encoded network holds no information of whether Oldenburg actually transferred information between the two or whether that connection was at all meaningful. In a flight network, Las Vegas and Atlanta might both have very high betweenness centrality because people from many other cities fly to or from those airports, and yet one is much more of a hub than the other. This is because, largely, people tend to fly directly back and forth from Las Vegas, rather than through it, whereas people tend to fly through Atlanta from one city to another. This is the type of information that network analysis, as it is currently used, is not well equipped to handle. Whether this shortcoming affects a historical inquiry depends primarily on the inquiry itself.

When deciding whether to use networks to explore a historiographical question, the first question should be: to what extent is connectivity specifically important to this research project? The next should be: can any of the network analyses my collaborators or I know how to employ be specifically useful in the research project? If either answer is negative, another approach is probably warranted.

## Texan Correspondence

You will need the information you [created in Module 3, after cleaning the correspondence data using Open Refine](/module-3/Exercises/).

### Umm, I never did manage that openrefine stuff...

In module 3, you used Notepad++ or Textwrangler, regular expressions, and OpenRefine to create a comma-separated value file (****.csv) of the diplomatic correspondence of the Republic of Texas. The final version of the file you created has a row for each letter listed in the volume, and in each row the name of the sender and the recipient. The file should look like this:

```
source,target
Sam Houston,J. Pinckney Henderson
James Webb,Alc6e La Branche
David G. Burnet,Richard G. Dunlap
...
```

This file is called 'an edge list' - it's a list of connections, or edges, between the individuals. If you no longer have the file, you can find it on [The Macroscope website](http://themacroscope.org/2.0/datafiles/texas-correspondence-OpenRefine.csv).  

## Quick instructions for getting the data into Gephi:

1. Open Gephi by double-clicking its icon. 
2. Click “new project.” The middle pane of the interface window is the “Data Laboratory,” where you can interact with your network data in spreadsheet format. This is where we can import the data cleaned up in OpenRefine. 
3. In the Data Laboratory, select “Import Spreadsheet.” 
4. Press the ellipsis “...” and locate the CSV you created. Make sure that the Separator is listed as “Comma” and the “As table” is listed as “Edges table.” 
5. Press “Next,” then “Finish.” Your data should load up. 
6. Click on the “overview” tab and you will be presented with a tangled network graph.

## Navigating Gephi

Gephi is broken up into three panes: **Overview**, **Data Laboratory**, and **Preview**. 

+ The **Overview pane** is used to manipulate the visual properties of the network: change colors of nodes or edges, lay them out in different ways, and so forth. The Overview pane is also where you can apply algorithms to the network, like those you learned about in the previous chapter. 
+ The **Data Laboratory** is for adding, manipulating, and removing data. 
+ Use the **Preview** pane to do some final tweaks on the look and feel of the network and to export an image for publication.

There is one tweak that needs to done in the Data Table before the dataset is fully ready to be explored in Gephi. 

1\. Click on the Data Laboratory tab.

2\. Click on the “Nodes” tab in the Data Table (this should be open already) and notice that, of the three columns, “Label” (the furthermost field on the right) is blank in every row. This will be a problem when viewing the network visualization, as those labels are essential for the network to be meaningful. 

3\. In the “Nodes” tab, click “Copy data to other column” at the bottom, select “ID”, and press “Ok” (Fig. 7.5). Upon doing so, the “Label” column will be filled with the appropriate labels for each correspondent. 

5\. While you’re still in the Data Laboratory, look in the “Edges” tab and notice there is a “Weight” column. Gephi automatically counted every time a letter was sent from correspondent A to correspondent B and summed up all the occurrences, resulting in the “Weight.” This means that J. Pinckney Henderson sent three letters to James Webb, because Henderson is in the “Source” column, Webb in the “Target,”, and the “Weight” is three.

6\. Clicking on the Overview pane will take you to a visual representation of the network you just imported. In the middle of the screen, you will see your network in the “Graph” tab. The “Context” tab, at the top right, will show that you imported 234 nodes and 394 edges. At first, all the nodes will be randomly strewn across the screen and make little visual sense. 

<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/s5_jgK5hEFA" title="Importing your data into Gephi" frameborder="0" gesture="media" allowfullscreen></iframe>
<br> 

7\. Fix the nodes by selecting a layout in the “Layout” tab – the best one for beginners is “Force Atlas 2.” 

8\. Press the “Run” button and watch the nodes and edges reorganize on the screen into something slightly more manageable. After the layout runs for a few minutes, re-press the button (now labeled “Stop”) to settle the nodes in their place. 

You just ran a force-directed layout. Each dot is a correspondent in the network, and lines between dots represent letters sent between individuals. Thicker lines represent more letters, and arrows represent the direction the letters were sent, such that there may be up to two lines connecting any two correspondents (one for each direction).
 
About two-dozen smaller components of the network will appear to shoot off into the distance, unconnected from the large, connected component in the middle. For the purpose of this exercise, we are not interested in those disconnected components, so the next step will be to filter them out of the network. 

9\. The first step is to calculate which components of the network are connected to which others; do this by clicking “Run” next to the text that says “Connected Components” in the “Statistics” tab on the right-hand side.  

10\. Once there, select “UnDirected” and press “OK.” 

11\. Press “Close” when the report pops up indicating that the algorithm has finished running. Now that this is done, Gephi knows which is the giant connected component and has labeled that component “0”. 

12\. To filter out everything but the giant component, click on the “Filters” tab on the right-hand side and browse to "Component ID Integer (Node)" in the folder directory (you’ll find it under "Attributes," then "Equal"). 

13\. Double-click "Component ID Integer (Node)" and click the "Filter" button at the bottom. Doing this removes the disconnected bundles of nodes.

There are many possible algorithms you could use for the analysis step, but in this case you will use the PageRank of each node in the network. This measurement calculates the prestige of a correspondent according to how often others write to him or her. The process is circular, such that correspondents with high prestige will confer their prestige on those they write to, who in turn pass their prestige along to their own correspondents. For the moment let us take its results to equate with a correspondent’s importance in the Republic of Texas letter network.

14\. Calculate the PageRank by clicking on the "Run" button next to "PageRank" in the "Statistics" tab. You will be presented with a prompt asking for a few parameters; make sure "Directed" network is selected and that the algorithm is taking edge weight into account (by selecting "Use edge weight"). Leave all other parameters at their default. 

15\. Press "OK".
 
16\. Once PageRank is calculated, if you click back into the "Data Laboratory" and select the "Nodes" list in the Data Table, you can see that a new "PageRank" column has been added, with values for every node. The higher the PageRank, the more central a correspondent is in the network. 

<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/nEAO04nQeQc" title="Modifying your network visualization" frameborder="0" gesture="media" allowfullscreen></iframe>
<br> 

17\. Going back to the Overview pane, you can visualize this centrality by changing the size of each correspondent’s node based on its PageRank. Do this in the "Ranking" tab on the left side of the Overview pane.

18\. Make sure "Nodes" is selected, press the icon of a little red diamond, and select PageRank from the drop-down menu. 

19\. In the parameter options just below, enter the "Min size" as 1 and the "Max size" as 10. 

18\. Press "Apply," and watch the nodes resize based on their PageRank. 

20\. To be on the safe side and decrease clutter, re-run the "Force Atlas 2" layout as described above, making sure to keep the "Prevent Overlap" box checked.
 
<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/kh9nR_W7B9w" title="Styling your network visualization" frameborder="0" gesture="media" allowfullscreen></iframe>
<br> 

At this point, the network is processed enough to visualize in the Preview pane, to finally begin making sense of the data. 

21\. In Preview, on the left-hand side, select "Show Labels," "Proportional Size," "Rescale Weight," and deselect "Curved" edges. 

22\. Press "Refresh." 

<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/2YBNnEmazq8" title="Previewing your final network visualization" frameborder="0" gesture="media" allowfullscreen></iframe>
<br> 

## So what have we got?

The visualization immediately reveals apparent structure: central figures on the top (Ashbel Smith and Anson Jones) and bottom (Mirabeau B. Lamar, James Webb, and James Treat), and two central figures who connect the two split communities (James Hamilton and James S. Mayfield). A quick search online shows the top network to be associated with the last president of the Republic of Texas, Anson Jones; whereas the bottom network largely revolves around the second president, Mirabeau Lamar. Experts on this period in history could use this analysis to understand the structure of communities building to the annexation of Texas or they could ask meta-questions about the nature of the data themselves. For example, why is Sam Houston, the first and third president of the Republic of Texas, barely visible in this network?

Write up your own observations on this process in your open notebook, and export your gephi file as a .graphml file (because Gephi's `.gephi` format is a bit unstable, always save as or export your work in a variety of formats). Upload that to your repository.
