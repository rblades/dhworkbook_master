# Close Reading with TEI

This worksheet, and all related files, are released CC-BY.

[By M. H. Beals](https://github.com/mhbeals/TEI-Close-Reading); Adapted for HIST3814o by S Graham

You will need the files in [this subfolder](https://github.com/craftingdigitalhistory/module3-wranglingdata/tree/master/tei-hist3907) so download that repository as a zip file and unzip it somewhere handy on your machine.

This exercise will explore a historical text and help you create a digital record of your analysis

### Vetting a Website ###

Visit the Recovered Histories Website at [http://www.recoveredhistories.org](http://www.recoveredhistories.org)

Examine the site's layout and read its introduction

+ What makes you believe this site is a trustworthy provider of historical texts?
+ What makes you believe this site is NOT a trustworthy provider of historical texts?

### Finding a Source ###

Visit the site's collections via the 'Browse' function

Locate the pamphlet *Negro Slavery* by Zachary Macaulay and open it

This is an abolitionist pamphlet regarding the Atlantic slave trade, presenting and examine evidence of how it is run.  When you approach a primary source like this, it is tempting to read through it from beginning to end, to get an overview of its contents, and then 'mine' or 'cherry-pick' good quotations to include in your assessments.  However, we are going to focus on examining a very small part of the text in a very high level of detail.  

### Setting Up Your Workspace ###

You will use your own machine rather than DHBox for this work. Arrange your workspace so that you have the scanned text of the pamphlet easily visible on one side of your screen. Open the 'blanktemplate.txt' file in [Sublime Text](https://www.sublimetext.com/), [Atom](https://atom.io/), [Textwrangler](http://www.barebones.com/products/textwrangler/) or [Notepadd++](https://notepad-plus-plus.org/) (or any text editor that understands encoding) and have that on the other side of the screen.

The last lines will be
<code>&lt;/body&gt;&lt;/text&gt;&lt;/TEI&gt;&lt;/teiCorpus&gt;</code>. Everything you write today should be just above <code>&lt;/body&gt;</code>.

### Transcribing Your Page ###

The first thing you will need is go to the tag

<code>&lt;biblScope&gt;1&lt;/biblScope&gt;</code>

and replace the number one (1) with the page number you are transcribing. Which page should you transcribe? Select a page in the document that you find interesting.

Next, you will need to *very carefully* transcribe your page of text from the image into your document.  Make sure you do not make any changes to the text, even if you think they author has used poor grammar or misspelled a word.  You do not need to worry about line breaks but should start every new paragraph (or heading) with a <code>&lt;p&gt;</code> and end every paragraph (or heading) with a <code>&lt;/p&gt;</code>.

Once you have completed your transcription, look away from your computer for 30-45 seconds.  Staring into the distance every 10-20 minutes will keep your eyes from straining.  Also, shake out your hands at the wrists, to prevent repetitive stress injuries to your fingers.  

### Encoding Your Transcription ###

You are now going to *encode* or *mark-up* your text.  

Re-read your page and highlight / colour the following things:

+ Any persons mentioned (including any he/she if they refer to a specific person)
+ Any places mentioned
+ Any claims, assertions or arguments made
Now that you have highlighted these, you are going to put proper code around them.

For persons, surround your text with these

``` <persName key="Last, First" from="YYYY" to="YYYY" role="Occupation" ref="http://www.website.com/webpage.html"> </persName> ```

+ Inside the speech marks for **key**, include the real full name of the person mentioned
+ In **from** and **to**, include their birth and death years, using ? for unknown years
+ In **role**, put the occupation, role or 'claim to fame' for this individual.  
+ In **ref**, put the URL (link) to the Dictionary of National Biography, Wikipedia or other biography website where you found this information. If there is a `&` in your link, you will need to replace this with &amp;amp;

For places, surround your text with these

```<placeName key="Sheffield, United Kingdom" ref="http://tools.wmflabs.org/geohack/geohack.php?pagename=Sheffield&params=53_23_01_N_1_28_01_W_type:city_region:GB""> </placeName>```

+ In **key**, put the city and country with best information you can find for the modern names for this location
+ In **ref**, put a link to the relevant coordinates on Wikipedia GeoHack website (http://tools.wmflabs.org/geohack/)
**To obtain this, go to the Wikipedia page for this city and click on the latitude/longitude coordinates for the location. For large areas, such as entire countries or continents, just use the Wikipedia page URL.**

For claims or arguments, surround your text with these

<code>&lt;interp key="reason" n="citation" cert="high" ref="http://www.website.com/webpage.html"&gt; &lt;/interp&gt;</code>

+ In **key**, explain why you believe this claim is true or not
+ In **n**, put a full citation to the relevant source
+ In **cert** (short for certainty), put: high, medium, low or unknown
+ In **ref**, put the link to the website where you got the information to assess this claim.

When you are happy with your work, hit save your work, give it a useful name, make sure it has .xml as the extension, and save it *and the .xsl file* to your repository.

> Alex Gill has made [The Short and Sweet TEI Handout](https://docs.google.com/document/edit?id=12ErwXGHGaFL71M3cWHpI6gkfVzzsKHfk7U6N6vRmIS4&authkey=CKG3l6oG&hl=en#heading=h.uy40z0-ctpi0) which you might want to explore as well. When you embark on encoding documents for your own research, [here are some questions to think about](http://www.wwp.northeastern.edu/outreach/seminars/_current/handouts/document_analysis.xhtml) to help you decide what kinds of tagging you'll need; these [templates from HisTEI](https://github.com/odaata/HisTEI/tree/master/frameworks/HisTEI/templates) might be useful (open the whole project with OxygenXML for full functionality, but you can copy those templates in any editor).

### Viewing Your Encoded Text ###

To see your encoded text, make sure your .xml and .xsl file are in the same folder. **Open either Internet Explorer or Firefox**. The following will not work in Chrome because it has different security settings.

Making sure both your (page number).xml file and your 000style.xsl file are in the same folder (or both on your desktop), drag the icon for (page number).xml into your Internet Explorer Browser window.

If you now see a colour-coded version of your text, Congratulations! If you hover over the coloured sections, you should see a pop-up with the additional information you entered.

If your text comes up only in black, with no paragraph divisions or headings, or doesn't come up at all, something has gone wrong. Re-open your .xml file and check that you have:

Placed `<p>` at the start of every paragraph, including the start of the page

Placed `</p>` at the end of every paragraph, including the end of the page

Made sure all your `<persName>`, `<placeName>` and `<interp>` tags are properly enclosed in `<>`s

Made sure you have both an open `<>` and close `<\>` tag for each tag you use

Made sure you attribute values are fully enclosed in `""`.

Made sure you have a space between the `"` of one attribute and the start of the next

Made sure you do NOT have a space after the `=` of an attribute

If your text still does not appear formatted, you may need to remove the text one paragraph at a time, refreshing your browser window, until it appears. This will help you identify which paragraph (or sentence) has the error within it).

### If you still don't see your text

*If you do not see the colour-coded version of your text, this might not necessarily mean that you've done something wrong*

+ Some browsers will not perform the transformation, for security reasons.
+ In which case, here's what we can do. If you are on a Windows machine using Notepad++, go to 'Plugins' >> Plugin Tools. (If you are on Windows but aren't using Notepad++, Sublime and Atom probably have a similar functionality, but you will have to search to figure it out.) Select 'XML Tools' from the list, and install it. You'll probably have to restart the program to complete the plugin installation. Open up the [1.xml](https://github.com/craftingdigitalhistory/module3-wranglingdata/blob/master/tei-hist3907/1.xml) file in Notepad ++. Then, under 'plugins'>>'xml tools" select 'XSL Transformation settings'. In the popup, click on the elipses: ``` ... ``` to open up the file finder, and select the ``` 000style.xsl ``` stylesheet. Click 'transform'. A new tab will open in Notepad++ _with a fully-formed html file displaying your data according to the stylesheet._ Save this, and then open it in a browser!

+ You can also check 'validate' from the XML Tools menu in Notepad++, which will identify errors in your XML. If you're still having errors, a likely culprit might be the way your geographic URLs are encoded. Compare what you've got with what's in the [1.xml](https://github.com/craftingdigitalhistory/module3-wranglingdata/blob/master/tei-hist3907/1.xml) reference document.

+ _Advanced_: If you install a [WAMP](http://www.wampserver.com/en/) or [MAMP](http://www.mamp.info/en/) server, and put your xml and xsl files in the WWW folder, you *should* be able to see the transformation no problem at ``` localhost\myxml.xml ``` (for example). (You can also use [Python's built in webserver if you have Python on your machine](http://www.pythonforbeginners.com/modules-in-python/how-to-use-simplehttpserver/) - all Mac users for instance do.)

> So here's the CND.xml, transformed into a csv: [http://shawngraham.github.io/exercise/cnd.xml](http://shawngraham.github.io/exercise/cnd.xml) . If you 'view page source', you'll see the original XML again! Save-as the page as whatever-you-want.csv and you can do some data mining on it.


### More on transformations

I made a file I've called [SG_transformer.xsl](https://github.com/hist3907b-winter2015/module3-wranglingdata/blob/master/tei-hist3907/SG_transformer.xsl). Open that file in your text editor. What tags would it be looking for in the xml file? What might it do to your markup? What line would you change in your XML file to get it to point to this stylesheet? Write all this down in your open notebook. It is a good habit to get into to keep track of your thoughts when looking at ancillary files like this.

If the nature of your project will involve a lot of transcription, you would be well advised to use an XML editor like [OxygenXML](http://www.oxygenxml.com/), which has a free 1 month trial. The editor makes it easy to maintain _consistency_ in your markup, and also, to quickly create stylesheets for whatever purpose you need. There are also a number of utility programs freely available that will convert XML to CSV or other formats. One such may be [found here](https://code.google.com/p/xml2csv-conv/). But the best way to transform these XML files is with XSL.
