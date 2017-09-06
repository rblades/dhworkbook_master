
#Module 3: Exercises

## Exercise 1

When we have text that has been marked up, we can do interesting things with it. In the previous module, you saw that XSL can be used to add styles to your XML (which a browser can interpret and display). You can see how having those tags makes for easier searching for information as well, right? Sometimes things are not well marked up. Sometimes, it's all a real mess. In this exercise, we'll explore 'regular expressions', (aka 'Regex') or ways of asking the computer to search for *patterns* rather than matching exact text.

This exercise follows a tutorial written for [The Macroscope](http://themacroscope.org).(Another good reference is [http://www.regular-expressions.info/](http://www.regular-expressions.info/)).

You should have [RegeXr](http://www.regexr.com/), an interactive tutorial that shows us what various regular expressions can do, open in a browser window somewhere so you can test your regular expressions out _first_ before applying them to your data!  We will use the power of regular expressions to search for particular patterns in a published volume of the correspondence of the Republic of Texas. We'll use regex to massage the information into a format that we can then use to generate a social network of letter writers over time. (You might want to give this tutorial a try, too: [Understanding Regular Expressions](http://programminghistorian.org/lessons/understanding-regular-expressions)).

What if you had *lots* of documents that you needed to clean up? One way of doing it would be to write a python program that applied your regex automatically, across all the files in a folder. *Optional advanced exercise*: [Cleaning OCR'd Text with Regular Expressions](http://programminghistorian.org/lessons/cleaning-ocrd-text-with-regular-expressions)

* Start with [a gentle introduction to regex](../supporting materials/regex.md) and then begin the [regex exercise](../supporting materials/regexex.md).

**remember to copy your history file and any other information/observations/thoughts to your Github repo**

## Exercise 2

*Open Refine* is the final tool we'll explore in this module. This engine allows us to clean up our messy data. We will feed it the results from Exercise 2 in order to consolidate individuals (ie, 'Shawn' and 'S4awn' are probably the same person, so Open Refine will consolidate that information for us). This exercise also follows a tutorial originally written for [The Macroscope](http://themacroscope.org).

Open Refine does not run in DHBox, so use the filemanager in DHBox to move your `cleaned-correspondence` file to somewhere safe on your computer.

[Visit the instructions in our supporting materials](../supporting materials/open-refine.md).

For more advanced usage of Open Refine, as an optional exercise you can also try [The Programming Historian's Tutorial on Open Refine](http://programminghistorian.org/lessons/cleaning-data-with-openrefine).

**remember to copy your notes and any other information/observations/thoughts to your Github repo**

## Your final project

You can use what you've been learning here to do some clean-up on the Shawville Equity files (or a subset of them, of course, as suits your interests - you have explored them, haven't you?). Google for 'sed patterns' and see if you can combine what you find with what you've learned in this module in order to clean up the text. For instance, a common error in OCR is to confuse the letter i with the letter l and the numeral 1. Shawville becomes Shawvllle. You could use grep to see if that error is present, and then sed to correct it. The file names are long, and there are several hundred; you might give this kind of thing a try too:

`find . -type f -exec sed -i.bak "s/foo/bar/g" {} \;`

This command finds all files in a folder and creates a backup for each one in turn before searching for 'foo' and replacing it with 'bar'.

This command: `grep "[b-df-hj-np-tv-xz]\{5\}" filename` will find all instances of strings of five consonants or more, which can be useful to give you and idea of what kinds of sed patterns to write.

Maybe, if you inspect the pdfs and the txt together, you can figure out patterns that set off interesting things in say the classified ads or the editorials - and then write some grep and sed to create new files with just that information. Then you could use Open Refine to further clean things up. Maybe the messiness of the data is [exactly the point](https://smgprojects.github.io/experiment-bad-equity/) ([and my workup on bad OCR](https://smgprojects.github.io/experiment-determining-bad-ocr-via-automated-spellcheck/)) you want to explore. Nevertheless:

**cleaning data is 80% of the work in digital history**.

**remember to copy your notes and any other information/observations/thoughts to your Github repo**

## Going Further

+ See some of the suggestions at the end of the [Open Refine exercise](../supporting materials/open-refine.md)

+ [Counting and Mining Data with Unix](http://programminghistorian.org/lessons/research-data-with-unix)

+ The *Stanford Named Entity Recognizer* is a program that enables you to automatically tag words in your corpus according to whether or not they are place names, individuals, and so on. The output can then be subsequently extracted and visualized, which you'll learn in Module 4. [Working with the Stanford NER](../supporting materials/ner.md).
