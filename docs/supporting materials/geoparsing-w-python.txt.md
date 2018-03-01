#Geoparsing with Python

This exercise draws from the work of [Fred Gibbs](http://fredgibbs.net/)

+ [extract, transform, and save as CSV](http://fredgibbs.net/tutorials/extract-transform-save-csv.html)
+ [extract geocoded placenames from a text file](http://fredgibbs.net/tutorials/extract-geocode-placenames-from-text-file.html)
+ [create a kml file with python](http://fredgibbs.net/tutorials/create-kml-file-python.html)

In this exercise, you will need to have Python installed on your machine. [You can download it from Python's website](https://www.python.org/downloads/). I have version 2.7.9 on this machine, and know that what follows works with that version.

You should also read and understand Fred Gibbs' tutorial on [installing python modules](http://fredgibbs.net/tutorials/install-python-modules) because you will need to install some helper modules.

In Module 3, you used the NER to extract place names from a text. After some further munging with regex, you might have ended up with a CSV that looks like [this one on GitHub](https://raw.githubusercontent.com/hist3907b-winter2015/module4-holes/master/texas.csv).

1. Use Openrefine to open that CSV file. In the same way you tidied up in the [Open Refine tutorial in module 3](https://github.com/hist3907b-winter2015/module3-wranglingdata/blob/master/openrefine.md), clean up this CSV so that you merge together place names appropriately (ie. so that '4ustin' gets merged with 'Austin'). Do this for all the columns.
2. Export the table as a new CSV &mdash; call it `cleaned-places.csv`.
3. Open that CSV in your spreadsheet program. Copy and paste all of the columns so that they become a single list. (ie. one column of place names).
4. Using your spreadsheet's filtering options, see if you can remove any more duplicates. (It might be useful to keep track of how many duplicates you delete, in a new file, eg -> Texas,200 <- that kind of information might be handy, as in [the mapping texts project (PDF opens in new tab)](http://mappingtexts.stanford.edu/whitepaper/MappingTexts_WhitePaper.pdf)).
5. Save the file you were removing the duplicates from (which has just a single column of unique place names) as 'placelist.txt'
6. Now, at this point, we're going to open up our text editor and create a new python program, following [Gibbs' tutorial](http://fredgibbs.net/tutorials/extract-geocode-placenames-from-text-file.html). His complete script is at the bottom of his post, but make sure you understand everything that is going on. Do you see the places where he has to import new python modules to make his script work? Make sure you've installed those modules. Let's call your completed script 'geoparse.py'. Done that? Good. 
7. Open your terminal, navigate to the folder you're working in, and run your script: ```python geoparse.py```

Did it work? Did you get an error message? It's entirely possible that you got this message:

```SHELL
Traceback (most recent call last):
  File "geolocate.py", line 14, in <module>
    lat = json['results'][0]['geometry']['location']['lat']
IndexError: list index out of range
```

...but check your folder. Do you have a ```geocoded-places.txt``` file? If so, it worked! Or at least, it got most of your places from the Google maps API. (For the rest, you can try uploading your places list to [Scargill's geoparser](https://www.ltg.ed.ac.uk/software/geoparser/) and then copying and pasting the output to an excel file. This parser will give you several columns of results, where the first column represents its best guess and the other columns other possibilities).

You can now import your geocoded places into many other software packages. Gibbs also shows us how to convert our list into KML, the format that Google Earth and Google Maps can read. [Try out Gibbs' tutorial](http://fredgibbs.net/tutorials/create-kml-file-python.html). You can double-click on the resulting KML file, and if you have Google Earth installed, it will open up there. Within google earth, you can start adding more information, other annotations... pretty soon, you'll have a complete map!

**Remember to upload your scripts & data & obersvations to your open notebook.**

(Incidentally, if you wanted to load this material into [Palladio](http://palladio.designhumanities.org/) you'd need a file that looked like this:

Place	Coordinates<br>
MEXICO	23.634501,-102.552784<br>
California	36.778261,-119.4179324<br>
Brazos	32.661389,-98.121667<br>

etc: that is, a tab between 'place' and 'coordinates' in the first line, a tab between 'mexico' and the latitude, and a comma between latitude and logitude. Best way to effect this transformation? Probably using Regex. It's unfortunate that Palladio doesn't accept straightforward place,latitude,longitude comma separated data).
