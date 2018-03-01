
# A quick introduction to R and RStudio

R is a powerful language for statistical exploring, visualizing, and manipulating all kinds of data, including textual. It is however not the most intutive of environments to work in. In which case, [RStudio](http://www.rstudio.com/products/RStudio/) is what we need. Fortunately, you already have this installed for you in your DH Box; however, if you want to have it on your own computer, go get R [from RStudio](http://cran.rstudio.com/) and then the [RStudio](http://www.rstudio.com/products/RStudio/). In DH Box, you sign into RStudio with your DH Box credentials.

Why do we bother with this? Why not just use Excel? One word: reproducibility. In Excel, the sequence of clicking that one does to do anything is next to [impossible to effectively communicate](https://www.practicereproducibleresearch.org/case-studies/benmarwick.html) to someone else. Excel also was built for business applications, and those biases are built into its dna ([which can have some nasty effects](http://www.bionews.org.uk/page_695210.asp).)

R allows us to do scripted analyses. We write out the sequence of transformations or analyses to be done, making a kind of program that we can then feed our data into. Once we have a workflow that does what we need it to do, it becomes trivial to re-use the code on other datasets. What's more, when we do an analysis, we can publish the scripts and the data. We don't have to taken an author's word for it: we can re-run the analysis ourselves or build upon it.

This course only touches in the lightest manner on the potential for R for doing digital history. Please see Lincoln Mullen's [Computational Historical Thinking with Applications in R](http://dh-r.lincolnmullen.com/) for more instruction.

For now, we'll do a quick whistle-stop tour of using RStudio to do some analysis in R.

![Screenshot of RStudio in DH Box. Click the green plus sign to start a new script](https://i.imgur.com/4Egckof.png)

You should always keep your research materials (scripts and associated data) organized in separate project folders. RStudio makes this easy for you. 

1. When you open RStudio to start a new project, click where it says 'project (none)' at the right hand side of the interface.

2. Click on the down arrow, and select new R project. 

3. Follow the prompts, and create it in a new directory. R keeps track of what you're up to in a project file, so that you can pick up where you left off. [You should also keep your code under version control as well](../supporting materials/git-rstudio.md) so that you can recover from disaster and/or share your code/data with collaborators; click on that link to get version control set up.

4. Sometimes, it might happen that RStudio crashes (this can be, in DH Box, related to memory issues). If that happens &mdash; if it just seems to 'hang' (and you've waited several minutes), you can refresh your browser, and go back to DH Box. You'll probably have to re-open your project file. 

5. Use the file panel at bottom right to find your \*.rproj file (your R project file) and click on it to re-open. 

6. Save your work often, from the File > Save menu.

    RStudio divides the screen up into four neat panes. 

    + The top left is for writing your analytical script (or code; I will use the two words interchangeably)
    + The bottom left is the console where the analysis actually happens
    + The top right is an environment pane which will show you the variables you've created, your history (commands you've run), and (once it's configured) git; indeed, other tools and plugins will appear as tabs here.
    + The bottom right gives you a preview of any plots or charts you create; once you create one if you click 'zoom' the chart will open in its own pop up so that you can see it better. The file explorer and the help text also appear under tabs in this box.

7. You write your script in the script box, and then you can get RStudio to run the code one line at a time by clicking on code >> run line (it runs the line of code where you left the cursor). If you select a number of lines of code and hit run line, all of that code will run. R scripts are text files that use .r as their file extension.

8. The console is where the action happens. Click down in the console. 

9. Type `3 + 5` and hit enter. RStudio will run the calculation: `[1] 8`! The [1] indicates that this is the first result. 

10. Now type `a = 3` and hit enter. Over in the top right, the 'environment' pane updates to tell us that yes, a has a value of 3. 

11. Now type `b = 5`. The environment updates accordingly. 

12. Now type `a + b`. Hey, we can do algebra! Anything you can do in excel, we can do in code here in RStudio. 

A very good introduction to how R (the language) works is at [Try R on codeschool](http://tryr.codeschool.com/), an interactive tutorial in your browser. Go give some of that a shot.
