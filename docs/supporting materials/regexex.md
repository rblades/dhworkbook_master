# REGEX and the Republic of Texas

Regex comes in several different flavours. A good text editor on your own computer like [Sublime Text](https://www.sublimetext.com/) or [Atom](https://atom.io/) can do Regex searches and replaces from the find-and-replace box; Word cannot do that. Remember, Regex searches for **patterns** in the text. The correspondence of the Republic of Texas was collated into a single volume and published with a helpful index in 1911. It was scanned and OCR'd by Google, and is now available as a text file from the Internet Archive. You can see the OCR'd text at [archive.org](http://archive.org/stream/diplomaticcorre33statgoog/diplomaticcorre33statgoog_djvu.txt). We are going to grab the index from that file, and transform it using regex.

There are several hundred entries in that index. You could clean them up by hand, deleting and cutting and pasting, but with the power of regex, we'll go from this:

```
Sam Houston to A. B. Roman, September 12, 1842 101
Sam Houston to A. B. Roman, October 29, 1842 101
Correspondence for 1843-1846 —
Isaac Van Zandt to Anson Jones, January 11, 1843 103
```

...to nicely CSV-formatted table like this:

```
Sam Houston, A. B. Roman, September 12 1842
Sam Houston, A. B. Roman, October 29 1842
Isaac Van Zandt, Anson Jones, January 11 1843
```

The change doesn't look like much, and you might think to yourself, 'hey, I could just do that by hand'. You could but it'd take you ages, and if you made a mistake somewhere, are you sure you could do this consistently, for a couple of hours at a time? Probably not. Your time is better spent figuring out the search and replace patterns, and then setting your machine loose to implement it.

Data formatted like this could be fed into a network analysis program, for instance, or otherwise visualized and analyzed (which we will do in the next module). Regex as we are going to use in this tutorial allows us to go from unstructured to structured data.

## Getting started

In [Module 2, Exercise 4](/module-2/Exercises/#exercise-4-apis), we learned how to automatically grab text using by interacting with APIs. In this particular exercise today, we'll quickly download the file using `curl` (it's like wget, though there are some [differences between the two commands](https://daniel.haxx.se/docs/curl-vs-wget.html). It's good to know both).

1. At the command line, type the following curl command:

        $ curl http://archive.org/stream/diplomaticcorre33statgoog/diplomaticcorre33statgoog_djvu.txt > texas.txt

    The `curl` command downloads the txt file and the the `>` pushes the result of the command to a file called `texas.txt`.

2. Open `texas.txt` with Nano and delete everything except for the index of the list of letters (we just want the index). 

    > a. To select a lot of text in Nano, you set a starting point (a mark) with ctrl+shift+6 (the 'carat' symbol: ^). 

    > b. Then hit the down arrow on your keyboard, and you will highlight the text. 

    > c. When you've selected everything you want, hit ctrl+k to cut the text.

    That is, you’re looking for the table of letters, starting with ‘Sam Houston to J. Pinckney Henderson, December 31, 1836 51’ and ending with ‘Wm. Henry Daingerfield to Ebenezer Allen, February 2, 1846 1582’. Your file will now have approximately 2000 lines in it.

    Notice that there is a lot of text that we are not interested in at the moment: page numbers, headers, footers, or categories. We're going to use regular expressions to get rid of them. What we want to end up with is a spreadsheet that is arranged in three columns:

        Sender, Recipient, Date

3. Scroll down through the text; notice there are many lines which don't include a letter, because they're either header info, or blank, or some other extraneous text. We're going to get rid of all of those lines too.

    We want to keep every line that has this information in it: Sender to Recipient, Month, Date, Year, Page.

4. Save the file in nano: ctrl+x, Y, enter 

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/4Qf334BqXm4?rel=0" title="Downloading and editing our correspondence" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

WARNING: Regex can be very tricky. When I'm working with regex, I copy and paste some of the text I'm working on into the box at [RegExr](http://www.regexr.com/) and fiddle with the pattern until it does what I want. In fact, spend some time looking at their examples before you go any further in this exercise.

## The workflow
We start by finding every line that looks like a reference to a letter, and put a tilde (a `~` symbol) at the beginning of it so we know to save it for later. Next, we get rid of all the lines that don't start with tildes, so that we're left with only the relevant text. After this is done, we format the remaining text by putting commas in appropriate places, so we can import it into a spreadsheet and do further edits there.

We're going to use the `sed` and `grep` commands at the command prompt in our DH Box. These commands work differently to achieve different goals.

+ sed (where the 's' means 'stream' and 'ed' means 'editor') works by first identifying text that matches a pattern, and then swapping in the text we want to have, like the following:

        $ sed 's/old text/new text/g' filename

+ grep works in the following way:

        $ grep 'PATTERN WE WANT' inputfile 

    The above will print the results to the screen. If we want to redirect the results to a new file, we add this to the end: `> outputfile`.


### Step One: Identifying lines that have correspondence Senders and Receivers in them

**Discussion:** Read in full before doing any manipulation of your text!

**If you were using a text editor on your own computer, you would modify your regex appropriately:**

+ **Notepad++:** press ctrl+f or search->find to open the find dialogue box. In that box, go to the 'Replace' tab, and check the radio box for 'Regular expression' at the bottom of the search box. 
+ **TextWrangler:** hit command+f to open the find and replace dialogue box. Tick off the ‘grep’ radio button (which tells TextWrangler that we want to do a regex search) and the ‘wraparound’ button (which tells TextWrangler to search everywhere). 
+ **Sublime text:** command+f (Mac) / ctrl+f (Windows) opens the 'find' box (and shift+command+f (Mac) / shift+ctrl+f (Windows) opens find **and** replace). Tick the `.\*` button to tell Sublime we're working with regular expressions.

**However, we're going to use the two commands sed and grep at the command prompt in DH Box**.

Remember from our basic introduction that there's a way to see if the word "to" appears in full. 

1. Type `$ grep '\bto\b' texas.txt`

    The results print out to the screen. This command finds every instance of the word "to" (and not, for instance, also ‘potato’ or ‘tomorrow’ &mdash; try `grep 'to' texas.txt` instead to see the difference).

    We don't just want to find "to", but the entire line that contains it. We assume that every line that contains the word “to” in full is a line that has relevant letter information, and every line that does not is one we do not need. 

    You learned earlier that the query `.+` returns any amount of text, no matter what it says. Thus, the pattern that we will build when we are ready to use the sed command will include `.+\bto\b.+` &mdash; therefore, we edit every line which includes the word "to" in full (no matter what comes before or after it) and we do not edit any of the lines which do not contain "to".

    As mentioned earlier, we want to add a tilde `~` before each of the lines that look like letters, so we can save them for later. This involves the find-and-replace function, and a query identical to the one before, but with parentheses around it, so it looks like the following

        (.+\<to\>)

    and the entire line is placed within a parenthetical group. Since this the first group in our search expression, we can replace that group with `\1` and put the tilde in front of it like so: `~\1`.

2. Copy and paste some of your text into [RegExr.com](http://RegExr.com). 

3. Write your regular expression (ie. what you're trying to find), and your substitution (ie. what you're replacing with) in the RegExr interface. 

4. Once you're satisfied that you've got it right, we put the complete expression into our sed command:

        $ sed -r -i.bak 's/(.+\bto\b.+)/~\1/g' texas.txt

    Where:

    + `-r` means extended regex. This saves us from having to 'escape' certain characters.
    + `-i.bak` means make a backup of the original input file, in case things go wrong.
    + `-'s/old-pattern/newpattern/g'` is how we find and switch what we're looking for. The final `g` means 'globally', everywhere in the file.
    + `texas.txt` is the filename that we're looking to change.

    <br />
    When you hit enter, the computer seems to pause for a moment, and then gives you the command prompt again. 

5. Type `ls` and you'll see that a new file, `texas.txt.bak` has been created.

6. Type `nano texas.txt` and examine the file. You should now have `~` (tilde characters) at the start of each entry of the index!

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/RQNyjSyQzjg?rel=0" title="Editing our file with grep and sed in the command line" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

If for some reason your file does not have the tidles, or you've mangled your original file, you can replace `texas.txt` with the backup file you made like the following: `$ mv old-file-name new-file-name`, thus, `$ mv texas.txt.bak texas.txt`. Use Nano to confirm that you're back to where you needed to be, and try again.

### Step Two: Removing lines that aren’t relevant

**Discussion**

After running the find-and-replace, you should note your document now has most of the lines with tildes in front of it, and a few which do not. The next step is to remove all the lines that do not include a tilde. **If you were using a text editor on your own computer**, the search string to find all lines which don't begin with tildes is `\n[^~].+ `

A ```\n``` at the beginning of a query searches for a new line, which means it's going to start searching at the first character of each new line. **However, given the evolution of computing, it may well be that this won’t quite work on your system.** For instance, Linux based systems use ```\n``` for a new line, while Windows often uses ```\r\n```, and older Macs just use ```\r```. These are the sorts of things that can drive us crazy, and so we digital historians need to keep that in mind! Since this will likely cause much frustration, your safest bet will be to save a copy of what you are working on, and then experiment to see what gives you the best result. In most cases, the syntax will be the following:

```
\r\n[^~].+
```

Within a set of square brackets ```[]``` the carrot ```^``` means search for anything that isn't within these brackets (in this case, the tilde ```~ ```). The  ```.+ ``` as before means search for every remainding character in the line as well. All together, the query returns any full line which does not begin with a tilde; that is, the lines we did not mark as looking like letters.

By finding all ```\r\n[^~].+``` and replacing it with nothing, you effectively delete all the lines that don't look like the index entries. What you're left with is a series of entries and a series of blank lines.

**But DH Box makes the regex process so much easier.**

We are simply going to get grep to find all the lines that have a tilde in them, and write them to a new file like the following:

        $ grep '~' texas.txt > index.txt

Use Nano to confirm that this is true. 

Wasn't that easy?

<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/TRI46x2zp2U?rel=0" title="Removing irrelevant lines in our correspondence" frameborder="0" gesture="media" allowfullscreen></iframe>
<br>

### Step Three: Transforming into CSV format

**Discussion**

To turn this text file into a spreadsheet, we'll want to separate it out into one column for Sender, one for Recipient, and one for Date, each separated by a single comma. Notice that most lines have extraneous page numbers attached to them; we can get rid of those with regular expressions. There's also usually a comma separating the month-date and the year, which we'll get rid of as well. In the end, the first line should go from looking like the following:

        ~Sam Houston to J. Pinckney Henderson, December 31, 1836 51

to looking like the following:

        Sam Houston, J. Pinckney Henderson, December 31 1836

such that each data point is in its own column.

You will start by removing the page number after the year and the comma between the year and the month-date. To do this, first locate the year on each line by using the regex:

        [0-9]{4}

We can find any digit between 0 and 9 by searching for ```[0-9] ```, and ```{4} ``` will find four of them together. Now extend that search out by appending ```.+``` to the end of the query; as seen before, it will capture the entire rest of the line. The following query:

        [0-9]{4}.+

will return, for example, "1836 51", "1839 52", and "1839 53" from the first three lines of the text. We also want to capture the comma preceding the year, so add a comma and a space before the query, resulting in the following: 

         , [0-9]{4}.+
 
which will return ", 1836 51", ", 1839 52", etc.

The next step is making the parenthetical groups which will be used to remove parts of the text with find-and-replace. In this case, we want to remove the comma and everything after 'year', but not the year or the space before it. Thus our query will look like the following:

        (,)( [0-9]{4})(.+)

with the comma as the first group `"\1"`, the space and the year as the second `"\2"`, and the rest of the line as the third `"\3"`.  Given that all we care about retaining is the second group (we want to keep the year, but not the comma or the page number), what will the **replace** look like?

Find the dates using a regex, and replace so that only the **second** group in the expression is kept. You might want to consult the introduction to regex again before you execute this one.

Remember, the first part of the sed command will be: `sed -r -i.bak` then the pattern to find, the pattern to replace with, and the file name. You want to use sed on the new `index.txt` file you made. Can you devise the right pattern? It will resemble the following:

        $ sed -r -i.bak the-pattern-to-find the-patter-to-replace-with index.txt

<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/syyFk2rhSc8?rel=0" title="Transforming our file into CSV format" frameborder="0" gesture="media" allowfullscreen></iframe>
<br>

### Step Four: Removing the tildes

+ Find the tildes that we used to mark off our text of interest, and replace them with nothing to delete them.

<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/eg3p5BN1oKs?rel=0" title="Removing the tildes before each line" frameborder="0" gesture="media" allowfullscreen></iframe>
<br>

### Step Five: Separating Senders and Receivers

**Discussion**

Finally, to separate the Sender and Receiver by a comma, we find all instances of the word "to" and replace it with a comma. Although we used ```\b``` and ```\b``` to denote the beginning and end of a word earlier in the lesson, we don't exactly do that here. We include the space preceding “to” in the regular expression, as well as the ```\b``` to denote the word ending. Once we find instances of the word and the space preceding it, ```to\b``` we replace it with a comma ```,```.

+ Devise the regex to find the word, and replace with a comma.

<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/ESj9_rYQ2jw?rel=0" title="Separating Senders and Receivers" frameborder="0" gesture="media" allowfullscreen></iframe>
<br>

### Step Six: Cleaning up

**Discussion**

You may notice that some lines still do not fit our criteria. Line 22, for example, reads "Abner S. Lipscomb, James Hamilton and A. T. Bumley, AugUHt 15, ". It has an incomplete date; we don't need to worry about these for our purposes. 

More worrisome are lines, like 61 "Copy and summary of instructions United States Department of State, " which include none of the information we want. We can get rid of these lines later in a spreadsheet. 	

The only non-standard lines we need to worry about with regular expressions are the ones with more than 2 commas, like line 178, "A. J. Donelson, Secretary of State [Allen,. arf interim], December 10 1844". Notice that our second column, the name of the Recipient, has a comma inside of it. If you were to import this directly into a spreadsheet, you would get four columns, one for Sender, two for Recipient, and one for date, which would break any analysis you would then like to run. Unfortunately these lines need to be fixed by hand, but happily regular expressions make finding them easy. The following query:

`.+,.+,.+, `

will show you every line with more than 2 commas, because it finds any line that has any set of characters, then a comma, then any other set, then another comma, and so forth. Use grep to find these.  

Lastly, at the top of the file, add a new line that simply reads "Sender, Recipient, Date". These will be the column headers. Make a copy as a CSV file by using the `cp` command in the DH Box command line like the following:

        $ cp index.txt cleaned-correspondence.csv

**Congratulations!**

<br>
<iframe width="560" height="315" src="https://www.youtube.com/embed/4bLRLWlQYG0?rel=0" title="Cleaning our file" frameborder="0" gesture="media" allowfullscreen></iframe>
<br>

You've now used regex to extract, transform, and clean historical text. As a CSV file, you could now load this data into a network analysis program such as [Gephi](http://gephi.org) to explore the ramifications of this correspondence network. Upload your file to your repository, and make a note of the original location of the file, the transformations that you've done, and the date/time. You will be using your `cleaned-correspondence.csv` file in the next exercise using [**Open Refine**](../supporting materials/open-refine.md), where we'll sort out some of the messy OCR (fixing names, and so on).

#### Regex patterns for Step Three to Step Six

The pattern you want in step three is

        $ sed -r -i.bak 's/(,)( [0-9]{4})(.+)/\2/g' index.txt

The pattern for step four is

        $ sed -r -i.bak 's/~//g' index.txt

The pattern for step five is

        $ sed -r -i.bak 's/(\b to \b)/,/g' index.txt

The pattern for step six is

        $ grep -E ".+,.+,.+," index.txt

**HOWEVER**, in DH Box, the command will use `-r` instead of `-E` like the following:

        $ grep -r ".+,.+,.+," index.txt

The `-E` tells grep to treat the pattern as an extended regex (regex with a few more bells and whistles). On DH Box, the flag would be `-r`.
