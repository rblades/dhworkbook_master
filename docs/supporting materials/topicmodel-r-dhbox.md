# Topic Modeling in R, DH Box version

In this exercise, we're going to grab the Colonial Newspaper Database from my GitHub page, do some exploratory visualizations, and then create a topic model whose output can then be visualized further in other platforms (including as a network in Gephi or other such package). At the appropriate point, I show you how to import a directory of texts rather than a single file of data, and to feed that into the script.

Go to your DH Box, and click on RStudio. At the right side where it says 'Project (NONE)', click and create a new project in a new empty directory. (If you want to put this directory under version control with git, so that you can push your work to your GitHub account, please read [the RStudio instructions](git-rstudio.md).)

In the script panel (top left; click on the green plus sign and select new R script if this pane isn't open) paste the following code and then run each line by putting the cursor in the line and hitting Code > Run lines.

        install.packages("mallet")
        library("mallet")
        install.packages("RCurl")
        library("RCurl")

In the future, now that you've installed these packages you won't have to again, so you can comment them out by placing a ```\#``` in front.

### How to fix RCurl Package installation error

When attempting to run `install.packages("RCurl")` you may get an error along the lines of 

```r
checking for curl-config... no
Cannot find curl-config
ERROR: configuration failed for package ‘RCurl’
```

To fix this, navigate to the DH Box command line and type `$ sudo apt-get install libcurl4-gnutls-dev`. When the installation is successful, you can now install RCurl by running the last two lines of the script:

```r
install.packages("RCurl")
library("RCurl")
```

<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/zYVqc0aNSgo?rel=0" title="Preparing RStudio for network analysis" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<br> 

## Importing data directly from the web

Melodee Beals has been using TEI to markup newspaper articles, creating the Colonial Newspapers Database (which she shared on GitHub). We then used GitHub Pages and an XLST stylesheet to convert that database into a [table of comma-separated values](https://raw.githubusercontent.com/shawngraham/exercise/gh-pages/CND.csv). We are now going to topic model the text of those newspaper articles, to see what patterns of discourse may lie within.

Now we want to tell RStudio to grab our data from our GitHub page. The thing is, RStudio can easily grab materials from websites where the url is `http`; but when it is `https` (as it is with GitHub), things get a bit more fussy. So what we do is use a special package to grab the data, and then shove it into a variable that we can then tease apart for our analysis.

```r
x <- getURL("https://raw.githubusercontent.com/shawngraham/exercise/gh-pages/CND.csv", .opts = list(ssl.verifypeer = FALSE))
```
That line reaches out to the webpage and grabs the information and puts it into a variable called `x`.

```r
documents <- read.csv(text = x, col.names=c("Article_ID", "Newspaper Title", "Newspaper City", "Newspaper Province", "Newspaper Country", "Year", "Month", "Day", "Article Type", "Text", "Keywords"), colClasses=rep("character", 3), sep=",", quote="")
```
Now we've created a variable called `documents` and the `read.csv` command read all of the data pulled into `x`, and tells R that `documents` has columns called "Newspaper Title" etc. When we only want information from a particular column, we modify the variable slightly (eg. `documents$Keywords` would only look at the information in the keywords column). Let's go on a brief digression and actually do that, and see what we learn about this corpus:

```r
counts <- table(documents$Newspaper.City)
```

We tell R to make a new variable called `counts`, and fill it with the information from the column 'newspaper city' in `documents`. It counts them up! Let's make a simple barplot:
```
barplot(counts, main="Cities", xlab="Number of Articles")
```
The plot will appear in the bottom right pane of RStudio. You can click on 'zoom' to see the plot in a popup window. You can also export it as a PNG or PDF file. Clearly, we’re getting an Edinburgh/Glasgow perspective on things. And somewhere in our data, there’s a mispelled ‘Edinbugh’. Do you see any other error(s) in the plot? How would you correct it(them)?

Let's do the same thing for year, and count the number of articles per year in this corpus:
```r
years <- table(documents$Year)
barplot(years, main="Publication Year", xlab="Year", ylab="Number of Articles")
```
There’s a lot of material in 1789, another peak around 1819, againg in the late 1830s. We can ask ourselves now: is this an artefact of the data, or of our collection methods? This would be a question a reviewer would want answers to. Let’s assume for now that these two plots are ‘true’ &mdash; that, for whatever reasons, only Edinburgh and Glasgow were concerned with these colonial reports, and that they were particulary interested during those three periods. This is already an interesting question that we as historians would want to explore.

Try making some more visualizations like this of other aspects of the data. What other patterns do you see that are worth investigating?

Now, let's return to getting our data ready to create a topic model. In the line below, note that there is a file called `en.txt` that it wants to load up. You need to create this file; it's a list of stopwords, or common words that we think do not add value to our model (words like 'the', 'and', 'of' and so on.) The decision of which words to exclude from our analysis is, of course, a theoretical position.

To create that file, click on the 'New file' icon in the tool ribbon and select new text file. This will open a blank file in the edit window here. Copy and paste the list of words at [en.txt](en.txt) into that blank file and save it as `en.txt`. This file was put together by Matt Jockers.

```r
mallet.instances <- mallet.import(documents$Article_ID, documents$Text, "en.txt", token.regexp = "\\p{L}[\\p{L}\\p{P}]+\\p{L}")
```
That line above passes the article ID and the text of our newspaper articles to the Mallet routine.  The stopwords list is generic; it might need to be curated to take into account the pecularities of your data. You might want to create your own, one for each project given the particulars of your project. Note that Jockers compiled his stoplist for his research in literary history of the 19th century. Your mileage may vary! Finally, the last bit after `token.regexp` applies a regular expression against our newspaper articles, cleaning them up.

<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/kMTFInx0qPw?rel=0" title="Importing data directly from the web" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<br>

## Reading data from a directory

This is an alternative way of ingesting documents for topic modeling. Earlier, you learned how to use wget and some other scripts to download full text documents from Canadiana.org as well as from the Library and Archives Canada (the Canadian war diary). The code below loads those documents into Mallet, after which you can proceed to build a topic model. In the command line, `cd` into your folder that has your downloaded materials. At the command line, `cd` into your folder, and type `$ pwd` to get the full path. Copy it, go back to RStudio, and paste it into the line below between the `"` quotation marks.

```r
documents <- mallet.read.dir("/home/shawngraham/war-diary-text")

# your path will probably look like /home/your-account-in-dhbox/your-folder-of-materials

mallet.instances <- mallet.import(documents$id, documents$text, "en.txt", token.regexp = "\\p{L}[\\p{L}\\p{P}]+\\p{L}")
```
**NB Do either one or the other, but not both: read from a file, where each row contains the complete text of the document, or read from a folder where each file contains the complete text of the document.**

<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/wcSQHccJrW8?rel=0" title="Reading data from a directory" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<br>

## Building the topic model

The 'correct' number of topics is going to require trial-and-error. You don't want too few, because that would hide the complexity of your data; too many, and you're starting to split hair.
```r
#set the number of desired topics
num.topics <- 20
topic.model <- MalletLDA(num.topics)
```
Now we’ve told Mallet how many topics to search for; this is a number you’d want to fiddle with, to find the ‘best’ number of topics. The next line creates a variable `topic.model` which will eventually be filled by Mallet using the LDA approach, for 20 topics. Let’s get some info on our topic model, on our distribution of words in these materials.

```r
topic.model$loadDocuments(mallet.instances)
## Get the vocabulary, and some statistics about word frequencies.
## These may be useful in further curating the stopword list.
vocabulary <- topic.model$getVocabulary()
word.freqs <- mallet.word.freqs(topic.model)
head(word.freqs)
```
It is handy to write our output to our project folder periodically; that way you can bring it into other programs if you want to visualize it or explore it further, or if you simply want to have a record of what was going on at a particular point. The line below uses the `write.csv` command, where the first element is the variable and the second the filename.
```r
write.csv(word.freqs, "word-freqs.csv" )
```
Word frequencies are handy to look at because it will tell you if you've got words that are 'drowning out' the others. Some of these words you might want to consider adding to your stop words list (and thus, going back to where we first created the `mallet.instances` and restarting the analysis). By the way, do you see how you might create a bar plot of word frequencies?

Now we hit the heavy lifting: generating a topic model. Some of the comments below are very technical; just make sure to run each line of code! (Original code here came from Ben Marwick's analysis of the [Day of Archaeology](https://github.com/benmarwick/dayofarchaeology).)

```r
## Optimize hyperparameters every 20 iterations,
## after 50 burn-in iterations.
topic.model$setAlphaOptimization(20, 50)
## Now train a model. Note that hyperparameter optimization is on, by default.
## We can specify the number of iterations. Here we'll use a large-ish round number.
## When you run the next line, a *lot* of information will scroll through your console.
## Just be patient and wait til it hits that 1000 iteration.
topic.model$train(1000)
## Run through a few iterations where we pick the best topic for each token,
## rather than sampling from the posterior distribution.
topic.model$maximize(10)
## Get the probability of topics in documents and the probability of words in topics.
## By default, these functions return raw word counts. Here we want probabilities,
## so we normalize, and add "smoothing" so that nothing has exactly 0 probability.
doc.topics <- mallet.doc.topics(topic.model, smoothed=T, normalized=T)
topic.words <- mallet.topic.words(topic.model, smoothed=T, normalized=T)
```

<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/dT4L5bC9Eew?rel=0" title="Building the topic model" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<br>

Congratulations! You now have a topic model. Let’s look at some of our topics. What are the top words in topic 7? Notice that R indexes from 1, so this will be the topic that mallet called topic 6:
```r
mallet.top.words(topic.model, topic.words[7,])
```
Now we’ll write the distribution of the topics by document (ie. newspaper article) to a CSV file that we could explore/visualize with other tools. Then, we’ll take a look at the key words describing each topic.

```r
topic.docs <- t(doc.topics)
topic.docs <- topic.docs / rowSums(topic.docs)
write.csv(topic.docs, "topics-docs.csv" )
# that file enables you to see what topics are most present in what issues/documents

## Get a vector containing short names for the topics
topics.labels <- rep("", num.topics)
for (topic in 1:num.topics) topics.labels[topic] <- paste(mallet.top.words(topic.model, topic.words[topic,], num.top.words=5)$words, collapse=" ")
# have a look at keywords for each topic
topics.labels

write.csv(topics.labels, "topics-labels.csv")
```
Some interesting patterns suggest themselves already! But a list of words doesn’t capture the relative importance of particular words in particular topics. A word might appear in more than one topic, for instance, but really dominate one rather than the other. When you examine the CSV files, you'll notice that each document is given a series of percentages; these add up to 1, and are indicating the percentage which the different topics contribute to the overall composition of that document. Look for the largest numbers to get a sense of what's going on. We could ask R to cluster similarly composed documents together though...

<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/LXjZFyJHNHM?rel=0" title="Training topics with MALLET" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<br>

## A simple histogram

```
plot(hclust(dist(topic.words)), labels=topics.labels)
```

Do you see any interesting clusters? Topics that end up in the same clusters we interpret as being related in some fashion. The plot is a bit crowded; in RStudio you can open it in a new window by clicking 'zoom' to see the dendrogram more clearly. You can also Google 'hclust cran-r' to find tutorials to make a better plot. One thing we can do is to plot it again without labels, to see the structure a bit better:

```
plot(hclust(dist(topic.words)))
```

<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/zbdhK0KKGPE?rel=0" title="Creating a simple histogram" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<br>

Now, if we want to get really fancy, we can make a network visualization of how topics interlink due to their distribution in documents. The next bit of code does that, and saves in `.graphml` format, which packages like [Gephi](http://gephi.org) can read.

```r
topic_docs <- data.frame(topic.docs)
names(topic_docs) <- documents$article_id

install.packages("cluster")
library(cluster)
topic_df_dist <- as.matrix(daisy(t(topic_docs), metric = "euclidean", stand = TRUE))
# Change row values to zero if less than row minimum plus row standard deviation
# keep only closely related documents and avoid a dense spagetti diagram
# that's difficult to interpret (hat-tip: http://stackoverflow.com/a/16047196/1036500)
topic_df_dist[ sweep(topic_df_dist, 1, (apply(topic_df_dist,1,min) + apply(topic_df_dist,1,sd) )) > 0 ] <- 0
```

<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/cGtHCOJga3U?rel=0" title="Clustering your data" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<br>


```r
install.packages("igraph")
# the line above would normally install igraph. However, the latest version is not compatible
# with this version of R. Thus, go to command line in DH Box, cd to the R folder, cd x86_64-pc-linux-gnu-library, cd 3.0 folder.
# wget the older version of igraph that'll work: https://cran.r-project.org/src/contrib/Archive/igraph/igraph_0.6-3.tar.gz
# then, at command line, run the following R command: $ R CMD INSTALL igraph_0.6-3.tar.gz
# this'll install igraph. Indeed, for any package you can look for older versions of it by slotting in
# the name of the package in the url above and browsing the archive.
# Remember, we're working with R version 3.03, from 2013, so we need stuff earlier than that.

# once installed, call it:
library(igraph)

# we transform the information from the previous code block into a network
g <- as.undirected(graph.adjacency(topic_df_dist))

# then we specify the layout and the number of iterations to make it pretty
layout1 <- layout.fruchterman.reingold(g, niter=100)

#then we plot it out
plot(g, layout=layout1, edge.curved = TRUE, vertex.size = 1, vertex.color= "grey", edge.arrow.size = 0, vertex.label.dist=0.5, vertex.label = NA)
```

When you look at this network, you can see clusters of documents by virtue of largely shared topics. We export this data in a text format called `graphml`, which can be opened by any text editor, and visualized in nearly any network analysis program for further refinement and analysis. It might be interesting to explore why some issues are so topically focussed, for instance.

```
write.graph(g, file="cnd.graphml", format="graphml")
```

<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/1VA-82Vhk8I?rel=0" title="Graphing your data" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>
<br>

There are many ways of visualizing and transforming our data. This document only captures a small fraction of the kinds of things you could do. Another good exploration is at [Matthew Jockers' website](http://www.matthewjockers.net/macroanalysisbook/expanded-stopwords-list/) or the [global stopwords lists](http://www.ranks.nl/stopwords/). [Ben Marwick does really fun things with the Day of Archaeology blog posts](https://github.com/benmarwick/dayofarchaeology) and indeed, some of the code above comes from Marwick’s explorations. Keep your R scripts in your open notebook, and somebody might come along and use them, cite them, improve them, share them! Keep also all your data. Visit [my own work for an example](https://github.com/shawngraham/ferguson).
