# Using Git with rstudio-pubs-static

Before you can use Git to keep track of your changes to your R project, you need to tell the Git program (which keeps snapshots of your changes) who you are. Do this with these two commands via the command line:
`$ git config --global user.email "you@example.com"``
`$ git config --global user.name "Your Name"`

Go back to R Studio. Under 'Tools' select 'Version Control' then 'project setup'. Under 'Version control system' select 'Git'.

You now have a new option in the pane at top right, beside 'environment' and 'history': 'git'. Click on 'git'.

The panel now displays all of the files created in this project folder. Tick off the ones you want to commit. Then click on the 'Commit' button.

![screenshot of the Git panel in RStudio](https://i.imgur.com/6CiY06Q.png)

A new window opens called 'RStudio: Review Changes'. This window shows you a preview of the text of each file, in green where material has been added, red where material has been deleted (these are the 'difs'). Add a commit message int the top right 'commit message' box.

You've now made a local commit to your git repository! If things go horribly wrong, you can roll back the changes. Now, let's setup your github repo for this.

Go to your github account. Make a new repository; initialize it with a readme.md

Back in RStudio, click on the 'more' gearwheel on the Git tab. Select shell (you could do this from the command line too, when you're in your project folder). This will open up a box into which you can type commands; we're going to tell Git the location of our remote repository, add that info into the config, and do two pulls.

open shell
```shell
$ git remote add origin https://github.com/YOUR-ACCOUNT/YOUR-REPO.git
$ git config remote.origin.url https://github.com/YOUR-ACCOUNT/YOUR-REPO.git
$ git pull -u origin master
$ git pull -u origin master
```
And you now can push your changes to your remote repository whenever you make a new commit. There is a variation of markdown called RMarkdown that enables you to embed working R code into a document, and then 'knit' it into HTML or slide shows or pdfs. When you push those to a Github repo, you are now making data publications! The official [R Markdown information is here](https://shiny.rstudio.com/articles/rmarkdown.html).
