# Graphing the Net

It may be that you are interested in the structure of links on the internet. Perhaps you'd like to see how a particular topic plays out across Wikiepedia. What you'd have to do is a **web-crawl**. Below are quick instructions for setting up a webcrawl, which will follow every link on a page to a particular depth, and echo the results through your browser into Gephi for visualization and analysis.

## You will need:

+ The Chrome browser with [Site Spider Mk II](https://chrome.google.com/webstore/detail/site-spider-mark-ii/gedjofgioahckekhpgknhchelbpdogok) installed
+ [Gephi](http://gephi.org)
+ [HTTP Graph Generator Plugin for Gephi installed](https://gephi.org/plugins/#/plugin/httpgraph)

**NB** You can install the graph generator plugin from **within** Gephi:

1. Select 'Tools' on the main menu ribbon at the top of the screen (and **not** the 'plugins' item).
2. Within 'Tools', select 'plugins' and then 'available plugins'
3. Search for 'HTTPGraph'
4. Tick off the box and install it. 
5. When finished, close and restart Gephi with a new project.

## Getting set up to scrape

1\. In Chrome, go to the settings page (the 'hamburg' icon at the extreme right of the address bar, or by typing ```chrome://settings/``` in the address bar. 

2\. Click on 'show advanced settings' at the bottom of the page.

3\. Scroll down to 'Network' and click on 'change proxy settings'. 

4\. In the popup that opens, click the 'connections' tab, and then the 'LAN Settings' button. 

**Another** popup will open. 

5\. Select the 'Use a proxy server for your LAN'. 

6\. Enter ```127.0.0.1``` for the address, and ```8088``` for the port. Now, whenever you go to a website, the info will be echoed through that port. We need to set Gephi up to hear what's being passed.

7\. Open Gephi and start a new project. 

8\. Go to 'file', then 'generate', and then 'http graph'. A pop up will open, asking you to specify a port. 

9\. Input ```8088```. Accept the defaults, and press OK. On the overview panel, nodes will begin to appear when you go to a URL in Chrome. 

## Begin the scrape

1. Go back to Chrome. 
2. Put in the URL that you want to start your scrape on, eg ```http://en.wikipedia.org/wiki/Archaeology```.
3. Click the SiteSpider II button in your toolbar. Site spider will open a popup asking you how far and how deep you want to scrape. 
4. Set the SiteSpider II parameters accordingly. 
5. Hit 'go' and then flip over to your Gephi window. You'll see the network begin to populate! Let it run as long as you want. 
6. When you're finished, save your network by 'exporting' it (on the file menu) as any other format than .gephi. I say this because I find sometimes the .gephi format is unstable. You can then filter your network for resources or html pages or what have you. I suggest deleting the node labelled 127.0.0.1 because that's your computer and it will throw off any metrics you choose to calculate. 

## What does it all mean?

Well, that depends.

For an example of why you might want to do all this, and what you might find, see ['Shouting Into the Void?'](http://electricarchaeology.ca/2014/05/01/shouting-into-the-void/) a piece where I tried to understand the shape of the archaeological web.
