# Topic Modeling in R On Your Own machine

In this exercise, we're going to grab an archived copy of Melodee Beals' Colonial Newspaper Database from my GitHub page, do some exploratory visualizations, and then create a topic model whose output can then be visualized further in other platforms (including as a network in Gephi). The walkthrough [can be found on the HIST3907b website](http://hist3907b-winter2015.github.io/module4-holes/tm-CND.html). Each gray block is something to copy-and-paste into your script window in RStudio. Then, put the cursor at the start of the first line, and hit ctrl+enter to get RStudio to execute each line. In the walkthrough, when you get to another gray block, just copy and paste it into your script window after the earlier block. Work your way through the walkthrough. The walkthrough gives you an indication of what the output should look like as you move through it. (The walkthrough was written inside R, and then turned into HTML using an R package called 'Knitr'. You can see that this has implications for open research! For reference, [visit the original Rmd (R markdown) file that generated the walkthrough](https://gist.github.com/shawngraham/7efd64c08a94c39a593f).)

**When you start RStudio the first time for this exercise** make sure to create a new project in a new directory.

By the way: when you run this line: ```topic.model$train(1000) ``` your console will fill up with data as it iterates 1000 times over the entire corpus, fitting a topic model to it. This is as it should be!

In this way, you'll build up an entire script for topic modeling materials you find on the web. You can then save your script and upload it to your open notebook. In the future, you'd be able to make just a few changes here and there in order to grab and explore different data.

Make a note in your open notebook about your process and your observations.

**Going further** If you wanted to use that script on the materials you collected in module 2, you would have to tell R to load up those materials from a directory, rather than by reading a CSV file. Take a look at [my script for topic modeling the Ferguson Grand Jury documents](https://github.com/shawngraham/ferguson/blob/master/R%20script/ferguson-topicmodel.R), especially this line:

```documents <- mallet.read.dir("originaldocs/1000chunks/")```

You feed it the path to your documents. If you are on a windows machine, the path would look a bit different, for instance:

``` "C:\\research\\originaldocs\\1000chunks\\"
```
