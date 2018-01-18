# Module 5 Exercises

## Omeka
Omeka is an open source Content Management System (CMS) for sharing digital collections and creating media-rich online exhibits. A CMS is a web program that manages content including graphics, text, videos, and more for a web site. A CMS allows users to upload their content via a Graphical User Interface (GUI) and organizes it into appropriate folder structures. Traditional websites are programmed from the ground up - everything from structure, to styling, to creating folders and specifiying where multi-media content is located. The main advantage of using a CMS is that it requires little to no actual, background-level programming. That being said, anyone can edit a CMS's source code files, add their own, or modify them to fit their needs. Most CMSs are built using PHP, a web scripting program used to dynamically create content. However, most CMSs are also accompanied by massive native and third party plugin libraries that allow users to modify their website without touching any source code. Examples of CMSs include Wordpress, Drupal, Grav, Known, Joomla, and many more. 

Unlike many popular CMSs, Omeka is not a blogging platform. Omeka is used to create online exhibits. Today we are going to create a simple online exhibit. 

Our overall steps are as follows:

1. Create a subdomain of your website where Omeka will live. This will allow you to host Omeka as an entity of its own on your website, keeping your main website separate.
2. Install Omeka through cPanel on Reclaim Hosting.
3. Create an online exhibit with several historical items.
4. Change the style of our Omeka site by modifying the CSS of our theme.  

## Creating a subdomain

1\. Login to your Reclaim Hosting account through the [Reclaim Hosting login page](http://portal.reclaimhosting.com/).

2\. In the client area, select the cPanel tab.

3\. Under the Domains section, select Subdomains. Typically a subdomain divides your overall website into distinct portions. For instance, you could have your landing page at `mysite.com`, your blog at `blog.mysite.com`, and your class work at `hist3814.mysite.com`. That way each subdomain could have different styles and serve different purposes, but still be connected to your overall domain. You can add as many subdomains to your site as you'd like. 

Subdomains are essentially just an easier way of organizing your files and showing distinct differences from your main domain. You could technically also do `mysite.com/blog` or `mysite.com/hist3814`. In that case, however, it seems expected they would all be styled similarly to `mysite.com`. Furthermore, it might cause difficulty to have, for example, Wordpress running your mysite.com and Omeka running `mysite.com/Omeka`. It's best to stick with your free subdomains.

4\. Enter the name of your online exhibit in the Subdomain field. You could simply put `omeka`, `omeka-test`, etc. or get more descriptive and say `commemorationexhibit`. Choose a title relevant to your Omeka site's purpose.

5\. Leave the Domain field set to your domain.

6\. The Document Root will be automatically created (an advantage of adding a subdomain!). I would not recommend changing this, but if you want to further organize your folder strucutre, you are able to change the location.

7\. Click the Create button. It will take a moment, but your new subdomain will be approved. 

**NB Since the subdomain has nothing in it, if you navigate to it now, you will see 'Index of/' showing the file structure. This is normal.**

## Installing Omeka 

1\. Navigate back to your cPanel home page. 

2\. Under the Applications section, select Omeka. 

3\. On the right hand side, click the '+ install this application' button. 

4\. Under the Location section, select the subdomain you created in the previous instructions. Do not choose your main `mysite.com` domain. Choose your `omeka.mysite.com` domain or your variant of it. You can choose the https or http version. Https is more secure.

5\. Delete cms under Directory (Optional). We want it installed to the root of our subdomain, not a folder called cms.

6\. Under the Version section, leave the settings as they are. Make sure 'I accept the license agreement' is selected. It's also good practice to allow it to update as needed and to allow backups.

7\. Under the Settings section, either create a new Administrator Username and Administrator Password or securely write down the Administrator Username and Administrator Password generated for you. (You can click Show Password to show it.) **You NEED the username and password to make changes to your Omeka site.**

8\. Add an Administrator Email.

9\. Change the Website Title to a fitting and appropriate title.

10\. Under Advanced, leave the settings as they are.

11\. Click the Install button. You will be redirected to 'My Applications'. The installation may take a minute to process.

12\. Select the middle link of your new Omeka application that says `omeka.mysite.com/admin` or your variant of the subdomain.

13\. Login using your Administrator Username and your Administrator Password.

14\. At the top of the admin page, click on Settings.

15\. Scroll down to the bottom. In the ImageMagick Directory Path field, type `/usr/bin`. Reclaim Hosting comes with ImageMagick preinstalled. ImageMagick resizes and generates thumbnails of your images.

16\. Click Save Changes.

## Uploading content to Omeka

For the purposes of this exercise, we will use the [Gatineau Valley Historical Society Fire insurance plans](http://www.gvhs.ca/research/maps/maps-fire-insurance.html) used in [Module 4, Exercise 8](#exercise-8-simple-mapping-and-georectifying). You are also allowed to use any historical sources to create an exhibit. Maybe you want to choose historical newspapers that have been digitized from the Library and Archives? Just make sure to note where you got your sources and, preferably, you can download them as images

1\. On the left hand side, select Collections.

2\. Click Add a Collection. 

3\. My new collection will be fire insurance maps. Under title, add Maps of the Gatineau Valley - Fire Insurance Plans. 

4\. Go through each metadata field and fill in as much information as you can about your collection.

5\. Under Add Collection, click Public to make your collection publicly viewable. Click Add Collection.

6\. On the left hand side, select Items.

7\. Click Add an item.

8\. Navigate to the [Gatineau Valley Historical Society Fire insurance plans](http://www.gvhs.ca/research/maps/maps-fire-insurance.html) or your own source of historical files.

9\. Using the information provided with first map, fill in as much information as you can about your item. 

10\. Click on the map image.

11\. Right click and save the image to your desktop or easy to reach folder. 

12\. Select the Files tab.

13\. Click Browse and choose your image file (note you cannot upload an image larger than 128MB).

14\. On the right hand side under Collection, select your Collection and make sure it is set to public.

15\. Click Add Item. It may take a few minutes to upload.

16\. On the right hand side, click the blue View Public Page button.

17\. Go ahead and upload several exhibit items. If you can find other items related to your collection elsewhere, that'd be great too. 

18\. Go to `omeka.mysite.com` or your variant of the subdomain to view how to page looks to the public.

## Styling our exhibit (and making it more accessible!)

1\. At the top of the admin page, click Appearance. The default theme is 'Thanks, Roy'. You can choose any theme you want. They are all different and each has different advantages and disadvantages for editing.

2\. For this exercise, we will use the 'Thanks, Roy' theme. 

**NB If you choose a different theme to modify, you may see different options. Proceed at your own intent.**

3\. Click the blue Configure Theme button. Each theme configuration allows you to change basic style and content settings.

4\. With the configuration page open in one tab, open your `omeka.mysite.com` to view the public page. Whenever you make an update, simply refresh the public page to view it.

**NB When editing your website, it's best to use your browser's incognito mode. Browsers cache certain files like CSS rules and images so they can load quickly when you revisit that website. If you are making constant changes, however, they will get cached and you might not be able to view any of your changes. Since incognito mode does not cache anything, you are viewing a 'fresh' page each time. If you are sure you did everything right and no changes appear, make sure to clear your cache and use incognito mode.**

5\. Notice the Browse Items and Browse Collections links on the left of your public page are a bit light and hard to read. In the configuration, copy the text colour hex code `#444444`.

6\. Go to the [Color Hex website](http://www.color-hex.com/) and search `#444444`. Hex codes are an internet convention where a series of numbers or numbers and letters correspond with a unique colour. 

7\. Scroll down to Shades of `#444444`. I think `#1b1b1b` looks dark enough.

8\. Navigate back to the Omeka configuration page and replace The Text and Links fields hex codes of `#444444` with `#1b1b1b`.

9\. On the right hand side, click Save Changes.

10\. Refresh the public page and notice the text darkens. This will help make your website more readable.

### Using browser tools to make design easier

1\. Navigate to your public Omeka page.

2\. Right click on the Featured Item text.

3\. Select Inspect Element. The browser inspection tool allows you to view the code behind a website. 

**NB Chrome and Firefox have great inspector tools. Not all browsers have these tools, however, notably Safari.**

4\. The font is not that easy to read either. We will change it, but first let's find the current font. Scroll down on the right hand side under the Rules tab until you see the body CSS. This rule shows the font is called PT serif

```
body {
    font-family: "PT Serif", Times, serif;
}
```

5\. Serifs are not very accessible fonts. Sans-Serifs are much more readable. Go to [Google Fonts](https://fonts.google.com/) to choose a new, more readable font.

6\. Search Roboto. Roboto is a clean, easy to read font.

7\. Click the red plus sign to select the font. It will add to a queue below.

8\. Click the black queue bar.

9\. Scroll to where it says Specify in CSS. 

10\. Copy the text that says `font-family: 'Roboto', sans-serif;`. We will add this rule to our CSS file.

11\. Navigate to your cPanel home page and select File Manager at the top of the page.

12\. On the left hand side click on the folder for your Omeka site. The folder should have the same name as your domain. For instance, if your site is called `omeka.mysite.com`, the folder will be called `omeka.mysite.com` unless you changed the name earlier.

13\. Double click each folder: Themes > Default > css

14\. Right click `style.css` and select Edit. Reclaim Hosting has some great editing tools within the cPanel so you don't have to make updates within your desktop text editor.

15\. Search `font-family` by hitting ctrl-f (Windows) or cmnd-f (Mac). We **ONLY** want to change the rules that say `font-family: "PT Serif", Times, serif;`.

16\. Use the search to replace each instance of `font-family: "PT Serif", Times, serif;` with `font-family: 'Roboto', sans-serif;`.

17\. Click the blue Save Changes button at the top right of the editor.

18\. Navigate to your Omeka site and refresh the page. Notice the font changes to Roboto.

19\. Use your browser's inspector to find out the rule of a specific element. 

20\. If you make any major mistakes and want to start from scratch, you can copy the original `style.css` [file from Github](https://raw.githubusercontent.com/omeka/theme-thanksroy/master/css/style.css) and paste it into your file and save the changes. This will revert it back to the original style.

It is important to note that for our purposes, we edited the default `style.css` file directly. This was to introduce you to CSS and making changes to the source code. Typically, you'd want to add a new file called, for example, `custom.css` and specify the path to that file in our source code. That way you keep your own changes distinct from the default source code files. However, that would involve editing different PHP rules which is beyond the scope of this exercise. This is very important for making upgrades. If your theme ever upgrades, you will lose all your changes if you only edited the default `style.css`. This applies to any file type. Therefore, you may want to keep a copy of your changes somewhere handy, like on your desktop.




# Module 5 Exercises

The exercises in this module are about colour, layout, and manipulating graphics - but not necessarily in that order. You might find 'Sprucing up a PDF in Inkscape' exercise useful, as well as the 'Typography', 'Colour', and 'Layout' exercises.

Finally: while we haven't explored the possibilities here, I do not want to leave you thinking that all digital history work is necessarily text based. To that end, if you are looking for a challenge or for exposure to something rather different, I suggest you at least bookmark my [series of tutorials on augmented reality, games, and 3d models for history and archaeology](https://github.com/shawngraham/ar-archaeology/tree/master/workshop%20materials).

[Sprucing up a PDF in Inkscape](#sprucing-up-a-pdf-in-inkscape) | [Typography](#typography) | [Colour](#colour) | [Layout](#layout) | [More](#more)

![Image showing Ukrainian Parliament fist fight three times: 1 the original; 2 the photo with the Fibonnaci Golden spiral overlayed; 3 the photo as a Renaissance painting](http://uploads.neatorama.com/images/posts/587/74/74587/1407463055-0.jpg)

[Ukraine fist fight](http://www.theguardian.com/artanddesign/2014/aug/06/accidental-renaissance-photojournalism-italian-painting-ukraine-frank-lampard)

## By the way: Raster versus Vector
The first thing to know is that graphic images come in two distinct flavours - raster, and vector.

Raster images are composed of pixels, such that if you zoom into them, they become a pointilist blur (if you remember **Ferris Beuller's Day Off**, there's a scene where Cameron stares and stares at a painting, falling into its individual points of colour). Vector images on the other hand are described by mathematical functions, of lines and arcs and areas. No matter how deep you delve into these kinds of images, the image is always sharp - because the zoom is just another function of the mathematics describing the image.

**Rasters:** blocks of colours

**Vectors:** descriptions of points and arcs

## Sprucing up a pdf in Inkscape

Some of the tools that we used in Module 4 give visual output as raster images, others as vectors. Sometimes, we would like to tweak these outputs to make them more visually appealling, or clearer, or more useful. A program like MS Paint is only useful for dealing with raster images (and then, only in certain kinds of cases). We need a program that can deal with both, and also, lets us edit the image by treating each edit we do as a mostly-transparent layer on top of the image. That way, we can add, rearrange, hide or reveal, our edits to create a composite image. A free program that is immensely useful in this regard is [Inkscape](https://inkscape.org/en/). Inkscape is also quite useful in that we can open a pdf file in it, break the visual elements of the pdf into individual layers, and then rearrange/touch up/fix them up to make them more esthetically appealing.

In this first exercise, we will take the plot we generated in Module 4's exercise on topic modeling in R where we made a bar chart showing the number of articles by year. In R we exported that plot as a PDF. In Inkscape, we can import that pdf and 'explode' it so that we can manipulate its parts individually. We are going to take the simple bar chart and make it more legible, more visually appealing, for incorporation on a webpage.

1. Download and install [Inkscape](https://inkscape.org/en/) 
**NB Mac the installation instructions are a bit more complicated for Mac. Pay attention and follow closely!**
2. Download the [pdf we generated in R called publication-year.pdf (this downloads the pdf)](https://github.com/hist3907b-winter2015/module5-humanitiesvisualization/raw/master/publication-year.pdf)
3. Open that pdf. It's a pretty plain graphic. Right away there are at least two things we could do to make it more visually appealling. We could change the orientation of the characters in the y-axis to make them more legible. We can highlight bars of interest. And we could apply a colour scheme more generally that would make our graphic legible to folks with colour-blindness (see the 'going further' section at bottom).
4. Start Inkscape. 
5. Click File >> Import >> and then navigate to where you save the 'publication-year.pdf'. 
6. Click Ok when you've got it selected. 
7. In the next pop-up, just accept the default settings and click 'ok'. Your Inkscape window should now look like this:
<br><br>![Image showing graph scaling in Inkscape](https://raw.githubusercontent.com/hist3907b-winter2015/module5-humanitiesvisualization/master/inkscape1.png)<br><br>
8. The pdf is now a layer in the new image you are creating in Inkscape. You can save this drawing, **with its information about the layers and what is in each one** by clicking File >> Save As. ([Visit Github for my version](https://raw.githubusercontent.com/hist3907b-winter2015/module5-humanitiesvisualization/master/exercise1drawing-final.svg)). 'SVG' stands for 'scalable vector graphic'. (SVG is a kind of text file that describes the complete geometry of your illustration).
9. Do you see the bounding box around the plot? If you grab any of those handles (the double-arrow things), you can make it bigger or smaller on your sheet. **To retain the image proportions, hold ctrl + shift as you drag.** 
10. We can't edit any of the other elements yet - we can't change the colour of the bars, or the fonts of the text. We have to tell Inkscape to 'explode' these elements into their own 'objects'. In the menu bar at top, got to Object >> Ungroup. There are now a series of overlapping bounding boxes around each object.
11. Zoom in (by pressing the + sign on your keyboard) so that you're looking at the numbers of the y-axis. We're going to rotate these by 90 degrees to make them more legible. Select the arrow icon from the toolbar on the left side of the screen.
12. Click on the '50'. You'll get a bounding box around it. 
13. Click Object >> Rotate 90 CW. The 50 is now rotated! Do the same for the other numbers. 
14. Save. (If you double-click on the number, you might trigger the 'text edit' function. If you do that, no problem - you can change the font, change the number... although if you did that, it'd be a bit dishonest, right? Click on the arrow pointer icon in the toolbar again to get out of the text-editing function).
15. Let's imagine, for whatever reason, that you wanted to change one of the bars to a different colour, to highlight its importance to your argument. With the arrow icon, click on one of the bars so that you get the bounding box around it. Then, click on one of the colours from the palette at the bottom. Boom! You've got a newly colourized bar. 
16. Save
17. Add a legend. Write it so that the important message you want your viewer to get is immediately clear. Choose a font from Inkscape's included fonts that **supports** your message.
18. To export your image so that you can use it in a website or paper, click Edit >> Select All in All Layers. Every element of your image will now have a bounding box around it.
19. Go to File >> Export Bitmap. Never mind the options in the popup; just hit 'Export'. Inkscape will automatically assign your drawing a name with .png; here's [my version on Github](https://raw.githubusercontent.com/hist3907b-winter2015/module5-humanitiesvisualization/master/g3161.png). **Remember** if you want to edit this image again later, hit the 'save' button to save it as an svg. The svg will preserve all your layer information, while the png file is the visual representation (the png is in fact a raster graphic). Most browsers can handle svg files, so you could use that in your website; programs like Word seem to be able to handle raster graphics better than they do svg. You might want to experiment. In any event, every journal has different requirements for image formats. You would export your image to whatever those specifications are.

### Going further

In [infoheap's tutorial on inkscape](http://infoheap.com/create-and-use-color-palettes-in-inkscape/), you will learn how to load a custom colour palette. Why might you want to do that? You should be designing your work so that it is as universally accessible as possible. Many folks are colour-blind. 

+ Use [Color Brewer](http://colorbrewer2.org/) to generate a colour-blind safe palette. 
+ Then look for the 'GIMP and Inkscape - GIMP color palette for this scheme.' 
+ Click on that link, and you'll get a text file with the scheme you generated. 
+ Use that scheme to alter the colours on your plot.

-----

## Typography

Typographic plays an important role in visual communication. It can do everything from reduce eyestrain (do a search for 'easiest fonts to read on screen') to communicate power and authority. Is it any wonder that strong bold capitals come to be known as 'Roman'? But first: [are you a comic sans criminal?](http://www.comicsanscriminal.com/)

In this exercise,

+ I want you to read and understand the section on [font choices from the Owl at Purdue](https://owl.english.purdue.edu/owl/resource/705/01/).
+ Then, play some rounds of [Typeconnection](http://www.typeconnection.com/index.php). Pay attention to why - or why not - various pairings work.
+ Then, I want to consider the document you will be preparing for me that accounts for your learning in this course - the document where you choose your best exercises from the modules and explain how your approach to history, data, the digital, etc, has changed over this course. What typographic pair would work best for you?
+ Finally, you'll make a webpage that uses those fonts and explains why they work.

The first part of this exercise then is to find a pair of fonts and to understand why they work best for you. 

1. Read the materials above, and once you're done with the Typeconnection site, go to [Google Fonts](https://www.google.com/fonts) and search for a pair that are **suitable for your purpose**. 
2. When you find a font you like, click the 'add to collection' button.
3. At the bottom of the screen, you'll see a link for 'use'. Click on this - google will ask you if you want to use any of the variants of the font. Tick off accordingly. 
4. Do you see the embed code that Google provides, and the code to integrate the font into your CSS (stylesheet)? Leave this window open - we're going to use it in a moment.
5. Make a new repository for this exercise. 
6. In your repository, click the button beside 'branch'. 
7. In the search box that opens, type in ```gh-pages```. This will create a version of your repository that can be served as a website. You're now in the gh-pages branch.
8. Click on the + sign beside the repository name. This will create a new file in your gh-branch of your repository. Call it ```myfontchoice.html``` <- the .html is important to specify; otherwise your browser will not know how to render your page.
9. You now need to put some html in there. I've written a simple webpage that will use two fonts from Google Fonts, and then applies the font to my text depending on whether or not it is a header, which you specify like this: ```<h1> this is a header in between header tags </h1>``` or a paragraph, which you specify like this: ```<p>blah blah blah a paragraph of text blah blah blah</p>```. My webpage is [on Github](https://raw.githubusercontent.com/hist3907b-winter2015/module5-humanitiesvisualization/master/fontexample.html); right-click the link and open in a new tab. Copy the html into your new html document. Commit your changes (ie. save).
10. Let's see what we've got. To see the website version of your gh-pages branch, you go to ```<yourusername>.github.io/<reponame>/myfontchoice.html``` <- ie, the final part of the url is the name of the document in your repo. Do that now. You should see a simple webpage, with two very distinctive fonts.
11. Now: let's slide your font choices into the html. Go to your html page in your gh-pages repo (ie, not the ```github.io``` version, but the ```github.com/<yourusername>/<repo>/myfontchoice.html``` version. 
12. Hit the edit button. Look closely at line 6. Do you see my two fonts? Do you see the pipe character between them? That tells google you want **both** fonts. 
13. Go look at the google fonts page again to grab the exact name for your fonts (ie. uppercase letters make a difference!) and paste them into line 5 appropriately.
14. Lines 8 and 14 specify which font to use for headers, and which font to use for body text. Change appropriately.
15. Change my silly text for a paragraph that explains what the fonts are, and why they work for this purpose. Commit your changes.
16. Go to the ```github.io``` version of your repository (if you forget the address, you can find it under the 'settings' button on your normal repository page when you're in the gh-pages branch). 
17. Reload the page a couple of times to clear the older version you've already looked at and to replace it with your version. Ta da! Not only have you thought carefully about typography and fonts, you've also learned how to serve a webpage from a Github repository.

**Hint** You could use this as the basics of your submission for assessment, for your exercises. Build a webpage, link to your evidence, embed your images... For basic html [W3schools has a really good guide to keep around](http://www.w3schools.com/html/default.asp).

-----

## Colour

There's a lot of bumpf out there on the 'pyschology of colour'. Google it to see what I mean ([Youth Designer has a good example](http://www.youthedesigner.com/graphic-design-resources/infographic-graphic-design-resources/infographic-a-color-guide-for-designers/)). A lot of what you see here isn't so much psychology as it is associations (and indeed, western associations, at that). Associations are important of course; you don't want to undermine your message by making some unfortunate connections.

+ In this exercise, I want you to take the webpage you developed in the previous exercise, and make two versions of it: one, where the colours support the broader message of the page (a prototype for your exercises assessment piece, remember?), and the other where the colours **undermine** that broader message. Explain, in both cases, how your colour choices enhance and/or detract.

> Alternatively, you can make a one page slide in powerpoint doing the same thing.

**Resources**

Below is a graphic & a movie to help with the theoretical side of things:

![Image showing color theory graphic](http://paper-leaf.com/wp-content/uploads/2010/01/ct_1920.jpg)

[Understanding the rules of color, Lynda.com](https://www.lynda.com/Graphic-Design-tutorials/Understanding-rules-color/419419/534020-4.html)

To learn how to style your webpage appropriately, you can [follow this tutorial on CSS from codeacademy.com](http://www.codecademy.com/courses/web-beginner-en-TlhFi/0/1?curriculum_id=50579fb998b470000202dc8b).

Colours in Cultures:

![Image showing colours in other cultures](http://infobeautiful3.s3.amazonaws.com/2013/01/1276_colours_in_culture.png)

-----

## Layout

'Layout' can mean different things in different contexts. A general overview on issues in layout is covered by ['What makes a design great, Lynda.com](https://www.lynda.com/Graphic-Design-tutorials/What-makes-design-great/419419/534011-4.html) and ['Exploring principles of layout and composition'](https://www.lynda.com/Graphic-Design-tutorials/Exploring-principles-layout-composition/419419/534012-4.html). The [Slideshare on effective layouts](http://www.slideshare.net/kernlearningsolutions/what-is-an-effective-layout-3435438) gives you a sense of things to watch out for as well.

For academic posters in particular, consider [these suggestions from the APA](http://www.apa.org/gradpsych/2011/01/poster.aspx).

In essence, good layout makes your argument legible, intuitive, and reinforces the rhetorical points you are trying to make. You should take into account 'principles of universal design' - consider some issues with [powerpoint](http://accessproject.colostate.edu/udl/modules/powerpoint/mod_ppt.php) and with [websites](http://accessproject.colostate.edu/udl/modules/html/mod_html.php) (although some of the technical solutions proposed in those two documents are a bit out of date, the general principles hold!)

In this exercise, you will design a new poster OR modify an existing poster. You can use either Inkscape or Powerpoint.

Inkscape:

1. Download one of the scientific poster templates from [Ugo Sangiorgi](https://github.com/ugosan/svg-conference-poster) (These are developed from [Felix Breuer's blog post](http://blog.felixbreuer.net/2010/10/24/poster.html); note his discussion on design). 
2. Open it in Inkscape. 
3. Make notes in your open notebook **from the point of view of layout:** what elements of the design work? What aren't working? How would you repurpose this poster to fit the requirements of the assessment exercise ([remember, details here](https://github.com/hist3907b-winter2015/syllabus/blob/master/exercise_assessment_guideline.md))?
4. [Visit Inkscape's website for help with the basics of Inkscape](https://inkscape.org/en/doc/tutorials/basic/tutorial-basic.en.html). 
5. Modify the poster, and upload the svg or pdf or png version to your repository.

PPT: 

There's a lot of information out there on making posters with powerpoint. 

1. Read [parts 1, 2, and 3 of the Make Signs tutorial](http://www.makesigns.com/tutorials/scientific-poster-parts.aspx) and then consider [Colin Purrington's advice](http://colinpurrington.com/tips/poster-design). Once you've read and digested, pick a poster from [Pimp my poster](https://www.flickr.com/groups/pimpmyposter/pool/) that strikes use. 
2. Make notes in your open notebook: **from the point of view of layout** what elements of the design work? What aren't working? How would you repurpose this posert to fit the requirements ot he assessment exercises ([remember to visit Github for the details](https://github.com/hist3907b-winter2015/syllabus/blob/master/exercise_assessment_guideline.md))? 
3. Grab a template from [from Colin Purrington's](http://colinpurrington.com/tips/poster-design#templates), and use it to prototype a poster that works. 
4. Upload the poster as a pdf to your repository.

If you want to explore layout in the context of webpage creation, I would point you to the the roster of lessons at [Codeacademy](http://www.codecademy.com/en/tracks/web). Same instructions: find an existing site that you will consider from the point of view of what works, what doesn't, and use that reflection to guide the construction of your own.
_____
## More

More resources, tutorials, and things to explore.

### Accessibility and Design
While most of this applies to websites, think also about how the general principles apply to other ways & means of telling our data stories.

+ [How People with Disabilities Use the Web](http://www.w3.org/WAI/intro/people-use-web/)
+ [Web Content Accessibility and Mobile Web](http://www.w3.org/WAI/mobile/overlap.html)
+ [Accessibility in HTML5](http://www.clarissapeterson.com/2012/11/html5-accessibility/)
+ [Web Accessibility Evaluation Tool](http://wave.webaim.org/)
+ [Considering the User Perspective](http://webaim.org/articles/userperspective/)
+ [Constructing a POUR Website](http://webaim.org/articles/userperspective/) Percievable, Operable, Understandable, Robust. Applies much wider than design of websites.
+ [Checking Microsoft Office-generated documents for accessibility](https://support.office.com/en-us/article/Check-for-accessibility-issues-a16f6de0-2f39-4a2b-8bd8-5ad801426c7f?CorrelationId=19c77f4b-7307-4697-9320-8bbbe05aa85a&ui=en-US&rs=en-US&ad=US)

### Infographics / Storytelling
#### Infographics

+ [The Difference between Infographics and Visualizations](https://eagereyes.org/blog/2010/the-difference-between-infographics-and-visualization)
+ [Design hints for infographics](http://piktochart.com/infographics-design-series-design-your-infographic-like-a-pro/)
+ [Piktochart](http://piktochart.com/)
+ [Infogr.am](https://infogr.am/)
+ [Infoactive.co](https://infoactive.co) (has a free option, but might not allow exports. You'd have to check).
+ [Easel.ly](http://www.easel.ly/)

#### Storytelling

+ [Creatavist](https://creatavist.com/)
+ [Medium](https://medium.com/)
+ [Cowbird](http://cowbird.com/)
+ [Exposure](https://exposure.co/)
+ [Timeline.js](https://timeline.knightlab.com)
+ [Storymap](https://storymap.knightlab.com/)

### ManyLines

[Manylines](http://tools.medialab.sciences-po.fr/manylines) is an application that allows you to create narratives from network graphs. In essence, you upload a network file in .gexf format (which you can export from Gephi) and it renders it on the screen. There are some layout options to make the graph more intelligible. Then, you take a series of snapshots zoomed in on the graph in different places, and add text to describe what it is that's important about these networks. The app puts a Prezi-like wrapper around your snapshots, and the whole can then be embedded in a website or be used as a standalone website. [Check out my first attempt on medialab.](http://tools.medialab.sciences-po.fr/manylines/embed#/narrative/051b0a7a-c1af-458f-b6a1-e3b0964e577f) 

You can also embed nearly anything in the narrative panels - youtube videos, [timeline.js](http://timeline.knightlab.com/), as long as you know how to correctly format an [iframe](http://www.w3schools.com/tags/tag_iframe.asp).  

To give this a try, why not use the Texan Correspondence network we generated in earlier modules? Export it in .gexf format from gephi, import to ManyLines, and go! The interface is fairly straightforward. Just follow the prompts.

**Caveat Utilitor** I don't know how long anything made with ManyLines will live on their website. But, knowing what you know about wget and other tools, do you see how you could archive a copy on your own machine? ManyLines is available on [Github](https://github.com/medialab/manylines) so you can certainly use it locally.

### Leaflet

Maps can be created through a variety of services ([tilemill](https://www.mapbox.com/tilemill/), [cartodb](https://cartodb.com/), [mapbox](http://mapbox.com), for instance). These can then be embedded in your webpages or documents. Often, that's enough. But sometimes, you'd like to take control, and keep all the data, all the map, under your own name, in your own webspace. Visit the gentle introduction to using [leaflet.js in our supporting materials](../supporting materials/leaflet.txt.md) to make, style, and serve your maps. [Visit a template on my Github repository](https://github.com/shawngraham/daea) for mapping with leaflet, drawing all of your point data and ancillary information from a csv file.

Oh, and Leaflet has [a list of background maps you can use](http://leaflet-extras.github.io/leaflet-providers/preview/index.html).

### Designing Maps with Processing and Illustrator

Nicolas Felton is a renowned designer. Watch [his 90 minute workshop on Skillshare](http://www.skillshare.com/classes/design/Data-Visualization-Designing-Maps-with-Processing-and-Illustrator/1063775924).

Caveat: I do not use Processing or Illustrator, but Processing is free and Inkscape can do many of the things that Illustrator does.
