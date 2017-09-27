# Getting yourself ready July 4th - 9th
![Black and white image of men standing around man in old fire fighter suit and air being pumped to him through a hose](https://c1.staticflickr.com/3/2197/2163099221_eb9ab72268.jpg)

"'Getting Ready for the Fire, Kasier Wilhelm' Bain Collection, Library of Congress hdl.loc.gov/loc.pnp/ggbain.10412 Call Number: LC-B2- 2400-7"

Welcome! This workbook is made by converting several plain-text files into a fully-operational website using the ['mkdocs' static website generator](http://www.mkdocs.org/). That means, if you want to keep a copy of all these files for your own records, you may. Simply click on the 'edit on github' link at the top right. This will bring you to the repository that houses this workbook. Then, when you're signed into 'github', you can 'fork' (that is, make a copy) the repo into your own account. Why 'forking'? It seems an odd phrase. Think of it like this:

Writing, crafting, coding: these are like a small river, flowing in one direction into the future. You get new ideas, new hunches: the river branches. There's a fork in its path. Sometimes new ideas, new hunches fold back into that original stream: they merge.

Github is a way of mapping that stream, and a guide to revisiting the interesting parts of it.

It's not the best metaphor, but it'll do. No doubt you've had that experience where, after working on an essay for days, you make a change that you regret. You wish you could go back to fix it, but ctrl+z only goes so far. You realize that everything you've done for the last week needs to be thrown out, and you start over.

Well, with 'versioning control', you can travel back upriver, back to where things were good. There are two tools that we will use to make this happen: [git](https://git-scm.com/) and [github](http://github.com). You'll learn more about making those things work in **module 1**. You'll see why you'd want to do that, and how to future-proof your work, writing things [in a plain-text format called 'markdown'](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

In **module 2**, we'll start exploring the wide variety of historical data out there. We'll talk about some of the ethical dilemmas posed by having so much data out there. 'Data' are not neutral 'things given'; rather, they are 'capta': things **taken**.

(Caveat: I am assuming, in this course, that the digital materials we want have already been digitized. Digitizing, adding meta-data (information that describes the data), and structuring it **properly** are very complex topics on their own that could be the subject of a complete course! If you are interested in those problems, a good place to start is this open course from SOAS on [database design for historians](http://port.sas.ac.uk/mod/book/view.php?id=75&chapterid=125).)

In **module 3**, we'll see that data/capta are **messy**, and that they make a kind of illusory order that as historians, we are not normally in the habit of thinking about. The big secret of digital history is that the majority of your time on **any** digital history project won't be finding the capta, won't be analyzing the capta, won't be thinking about the historical meaning of the capta. We'll be **cleaning it up**. The exercises in this module will help you do that more efficiently (and be aware that 'efficiency' in computing terms is not a theoretically neutral idea!)

In **module 4**, we talk about doing the analysis. I present finding, cleaning, and analyzing as if they were sequential steps, but in reality they are circular. Movement in one aspect often requires revisiting another one! This module explores how we do this, and what it means for us as historians.

In **module 5**, we begin at last to think about how we communicate all of this to our audiences. Look at how [one university lays out the expectations for digital history work](http://historyarthistory.gmu.edu/graduate/phd-history/digital-dissertation-guidelines) (and, do you see how this ties back to ideas about [paradata](http://site.craftingdigitalhistory.ca/rubric-and-assessment.html#final-project)?). We will think about things like typography and layout. We'll look at ways of making our visualizations more compelling, more effective.

Finally, while there is no formal requirement for you to do this, it would be a great way of launching yourself as a digital historian to think about how you would formally reveal your project work in this class to the wider world: and then do it. There's a lot of noise on the internet, especially when it comes to history. How do you, as a digital historian, make the strongest possible signal?

## What you need to do this week

1. Follow the instructions below to set up your digital history workspace
2. Annotate the course manual for any parts of it that are unclear (or alternatively, that have you excited)
3. Respond to the readings and the reading questions by annotating the readings themselves - see the instructions below.
4. [Submit your work to the course submission form](http://site.craftingdigitalhistory.ca/rubric-and-assessment.html#submitting-evidence)

## Setting up a your workspace

A digital historian needs to have a digital workshop/lab/studio/performance space. Such a space serves a number of functions:

- a scratch pad / fail log and code repository so that we remember what we were doing, or (more importantly) **what** we we did - that is to say, the actual commands we typed, the sequence of manipulations or [data moves](http://liu.english.ucsb.edu/data-moves/)
- a narrative that connects the dots, that explains the **why** of that what and how. You can use this narrative to point to when sharing your work with others. Digital history is not done in isolation or in a vaccuum. Sometimes, you will need to share a link to your work (often on twitter) asking, 'does anybody know why this isn't working?' or, 'does anybody know a better way of accomplishing this?', or, 'hey, I'm the first to do this!'
- a way of keeping notes on things we've read/come across on the web. There are a number of ways of accomplishing this. In this course, I will mandate one particular solution: ([hypothesis](http://web.hypothes.is)).
- when you're working with academic databases such as JSTOR, then you'll also need a bibliography manager. We don't go into this aspect very much in this course (if you take other courses with me, you will) but you might want to check out [Zotero](http://zotero.org).
- it can sometimes be useful to make little videos of your work to explain when something isn't working - [Screen-cast-o-matic](http://screencast-o-matic.com/) is free and does a good job

Now, the final part of your studio/lab/workshop is a domain (website + complete access to the webserver that powers it, so that you can install other platforms/services) of your own. A typical setup will be something along the lines of:

1. your-domain-name.org for your narrative, annotations, and anything you build regarding your work
2. github.com/your-name for your scratch pad and code repository

On your blog/narrative, you'll have a page that collates all of your web annotations as well. You'll also have - typically - an 'about' page where you can signal the kinds of history you're interested in, and the preferred way for people to get in touch with you. You do not have to use your real name. Remember the [real names policy](http://site.craftingdigitalhistory.ca/rubric-and-assessment.html#real-names-policy)

Because you have complete access and control over your domain, you can install other services as well. For instance, maybe you use Dropbox or Google Drive to sync your files across machines, or to function as a backup? You can install a service called 'OwnCloud' on your own domain that does the same thing, so that you have control over all your own materials.

So let's get started.

### Reclaim Hosting

In the course space for cuLearn, I gave you a code to use to pay for a domain of your own. I have already purchased domain space for you from an academic web hosting service, [Reclaim Hosting](https://reclaimhosting.com/shared-hosting/). This space will last for one year, at which point you have the option of paying to renew it or letting it die. Previous students in this course have used their domain to help with their applications for jobs and graduate school. One such is [Melissa](http://theproudhistorynerd.com).

1. You will be asked for the name you want to have for your space. You need to be thinking of branding here. Think of a professional name that conveys something of your personality and approach to history. I for instance own the domain, 'Electric Archaeology', which I chose to convey that I'm interested in digital archaeology, but also, that I move fast and cover a lot of breaking develops in the field (hey. It's my blog. I like the name). Please choose wisely. Some combination of your first and last name is often the best idea, since your own name is your own best calling card ('shawn graham' is such a generic name, that it was already long gone by the time I started doing digital history). Type in a name, select a top-level domain (ie, .com, .ca, .org, etc. I'll suggest .ca), and click on the 'check availability' button.
2. If the pop-up says 'congratulations, domain available!' then click on the continue button. (You may be offered free id protection, where Reclaim Hosting will hide your details is someone does a 'who-is' search on the domain name. If it does, then tick off the check box to confirm that you want this, and hit continue).
3. On the next screen, (the billing screen) fill in all of the information. The balance should be $0. At the bottom left, it will also say that you’ve used a one-time promotional code. Hit the green button at the bottom to complete the purchase (which is not costing you anything).

Congratulations! You now own your very own domain. **It might take a bit of time for your domain to appear live on the web**. During this time, you can log into your cPanel and install wordpress and so on - see below.

Giving you a space of your own is my political act of protest against the centralization of learning inside learning management systems. Learning isn't 'managed', it's cultivated. Unlike cuLearn, I cannot monitor your activity inside your own domain. I can only see what you choose to make public. Unlike Facebook or Snapchat or Instagram, I am not trying to monitize your personality on the web.

### Wordpress for your blog

Wordpress is probably the best option for a platform for writing the narrative bits of your digital history work.

1. Click the 'client area. It will tell you that you have one active account (with Reclaim Hosting) and one active domain. When the time comes to renew your account or to close it down, this is where you do it. Note also that there is a link to 'Support', which will put you in touch with Reclaim Hosting's help desk. They are extremely fast and good at providing support; always treat any help request you make with them **as if** you were writing a formal email to me. Be polite and considerate, and thank them. The owners of the business often are the ones who provide the help! Without them, we couldn't do this class.
2. Go to 'cPanel' - this is where you can install all sorts of different kinds of software on your account. Search for and select 'web applications'
3. Click on Wordpress. Then click on 'install this application'.
4. The next screen presents you with a number of options. Leave these set to their defaults. For 'location', leave this blank (you want to leave the directory option blank). That tells the installtron to put Wordpress at your-domain.ca . (When/if you install other pieces of software, you'd change this variable so that the new software doesn't overwrite this software!)
5. Further down the page, under 'settings', you need to change 'administrator username', 'administrator password', 'web site title', 'website tagline'. **this is the username and password to actually do things with your blog, and the name of your blog itself**. Leave everything else alone.
6. Click Install!
7. Once it's done, the installer will remind you of the url to your site, and the url to the blog's dashboard (where you go to write posts, make changes to the look and feel of the site). Open these in a new browser window, and bookmark them. To login to your blog, remember to go to the dashboard URL (eg. http://your-domain.ca/wp-admin), enter your blog administrator username and password.

You can close the cPanel webpage now (log out first).

#### Customising your blog

If you look at the dashboard for your blog, you'll see a lot of options down the left hand side of your screen. If you want to change the look of your blog, click on 'appearance' then click on 'themes'. A number of themes are pre-installed. You can click on the different themes and select 'preview' to see how your blog might look. When you find one you like, select 'activate'. Go to the other browser window where you have your-domain.ca open. Reload the page to see the changes take effect!

> If you're the sort of person who likes to sketch ideas out on paper, Lauren Heywood of the [Disruptive Media Learning Lab](http://dmll.org.uk/) has designed a paper-based exercise to prototype ideas. Why not give it a try? [Print this PDF of Wordpress design](http://dmll.org.uk/wp-content/uploads/2017/06/plan-your-wordpress-site-with-paper-dmll.pdf) and follow the instructions.

To write new content, know that there is a difference between a 'post' and a 'page'. A page is a new link on your site, while posts appear in chronological order on a page, with the most recent on top. Most themes show the most recent post by default, and pages appear in any menus on the site. **When you are logged into your blog** any post or page will have an 'edit' button at the bottom that you can click. You'll then be presented with an editing box with the standard toolbar across the top (allowing you to change the font, insert images, change the alignment of the text and so on). At the top right will be a button to save or publish/update the post/page.

+ Your blog will have a default 'about' page. Change that default text now to reflect something about who you are and why you are taking this course

To create new pages, you click on the 'pages' link in your dashboard and select 'add new'

To create new posts, you click on the 'posts' link in  your dashboard and select 'add new'.

Explore the options for your blog; customize and make the space your own.

**Password protected posts** If for any reason you feel that you don't want a post to be viewable by the web-at-large, you can hide it behind a password. At the top right where the 'publish' button hides, click on 'visibility' and select 'password protected'. Remember though: you'll have to share the password with me for grading purposes.

![Visibility Options in Wordpress](https://codex.wordpress.org/images/7/70/visibility.jpg)

For more information about controlling visibility of your posts and so on, [visit the Wordpress content visibility help page](https://codex.wordpress.org/Content_Visibility).

### Hypothesis

Hypothesis is an overlay on the web that allows you to highlight or annotate any text you come across (including **inside pdfs**). All of your annotations can then be collected together. It is a very effective research tool.

1. Create an account with [hypothes.is](https://web.hypothes.is/start/).
2. Get the [hypothes.is plugin for chrome](https://chrome.google.com/webstore/detail/hypothesis-web-pdf-annota/bjfhmglciegochdpefhhlphglcehbmek). If you don't have/use chrome, go to [the hypothes.is start page](https://web.hypothes.is/start/#) and click on the 'other browsers' link.

Once you're logged into Hypothes.is, and you have the plugin installed, highlight THIS TEXT and leave an annotation! Who will be first? There are a few different kinds of annotations you can make; [here is a list with videos showing them](https://web.hypothes.is/blog/varieties-of-hypothesis-annotations-and-their-uses/).

If you need step-by-step instructions for installing and using Hypothes.is, please [visit the Hypothesis help page](https://web.hypothes.is/quick-start-guide-for-students/) and/or watch this video:

<iframe width="560" height="315" src="https://www.youtube.com/embed/MjSpol-oPm4" frameborder="0" allowfullscreen></iframe>

Annotations are public by default. When you are making a new annotation you can toggle the visibility so that they are private and so visible only to you.

You can also 'tag' any annotation you make. If many people use the same set of tags, you can collect annotations by tag. This can make it easier to do group research projects, for instance.

**Please always tag your annotations with 'hist3814o'. That way, everyone's tags will show up on [the course Hypothesis page](http://jonudell.net/h/facet.html?facet=tag&mode=documents&search=hist3814o)**

#### Collecting your own annotations on your blog

Hypothesis has an **API** that allows you to do some neat things. 'API' stands for 'application programming interface', which is just a fancy way of saying, 'you can write a program that interacts with this web service'. [Kris Shaffer](http://pushpullfork.com/), a professor at the University of Mary Washington, has written a **plugin** for Wordpress that allows you to automatically collect annotations you make across the web and to display them all on a single page on your blog. So, we'll go get that plugin and install it on your blog:

Open [https://github.com/kshaffer/hypothesis_aggregator](https://github.com/kshaffer/hypothesis_aggregator) in a new browser window.

1.  Click “Clone or Download” (the green button at the top right).
2. In the pop-up, click 'Download ZIP'
3. Go over to the dashboard for your blog (if you closed this, you can get there again by opening a new browser window and going to your-domain.ca/wp-admin)
4. In the dashboard, click on Plugins >> Add New
5. Click “Upload Plugin”. It will open a window asking you to find and select the zip file you downloaded. This is probably in your 'downloads' folder. Select and click ok.
6. Once it’s uploaded and installed, click “Activate"
7. In the dashboard, click on 'pages' then add a new page. Call it 'Web Notes' or 'Annotations' or something similar.
8. Shaffer has created a 'shortcode' that tells Wordpress to go over to Hypothes.is and grab the latest information. So, in the text of your new page (in the editor window, make sure to click the 'text' button or else this won't work), enter the shortcode that will grab all of your public annotations: `[hypothesis user = 'kris.shaffer']` where you remove the `kris.shaffer` and put in your own Hypothes.is username.
9. Hit the 'publish' button. Wordpress will report that the page has been published and give you a link to it; click on this link to see your new always-updating list of annotations! Of course, if you haven't made any public annotations yet, nothing will display. Go annotate something, then come back and reload the page.

### Github

Finally, you need a github account. We will go into more detail about how to use Github in the next module. For now, go to [Github.com](http://github.com) and sign up for a new account. Follow all the prompts, and make a note of the direct URL to your account (mine for instance is [http://github.com/shawngraham](http://github.com/shawngraham)). Put this link in your 'about' page on your blog. You'll learn how to use this space in exercise 3 in module 1.

### Your digital history lab/studio/workshop

You now have a digital history lab equipped with all of the necessary ingredients for doing digital history. You have an open notebook for recording what you are up to (both your narrative and your annotations). In Github, you have a scratch pad for keeping track of the actual nuts-and-bolts of any digital work you do (and note that it is entirely possible to do digital history successfully without having to do anything that a computer scientist for instance would call coding). You have a domain that you control completely, and where you can install other platforms and services as seems necessary.

### VPN & DH Box

To access our virtual computer, the DH Box, you will need to use Carleton's VPN service. Please visit [Carleton's VPN help page](https://carleton.ca/its/help-centre/page-type/vpn/) and follow the instructions for your particular computer. Once you've got it installed, you will need to connect to Carleton through the VPN with your mycarletone credentials. Indeed, you should always connect via a VPN whenever you're using a public wifi point (like in coffee shops). The VPN acts like a private tunnel from your computer to Carleton's servers. To the rest of the internet, it will now look as if you actually are on campus. Once you're connected via the VPN, you can [access the DH Box through your browser](http://134.117.26.132:5000/). Bookmark the site; you'll use it in the exercises in module 1.

#### Using the DH Box

1. Click the 'sign up' button
2. Fill in the form. Choose a username and password that you'll remember. You don't have to use a real email by the way, just something that looks email-like (this is handy if, like me, you end up creating multiple DH Boxes - it's a bad idea to have more than one DH Box with the **same** email address)
3. Select the most time available (which will either be 1 or 2 months).
4. Your personal DH Box will be created. Your username will now appear in the top right hand side of the purple bar. To enter the DH Box, click the username, select 'apps'.
5. A new tool ribbon appears below the purple bar. Most of what you will do in this course involves the 'command line', 'R studio', and 'File Manager'.
6. Anytime the command line or R Studio should ask for your username or password, you use the DH Box username and password you just created.

**A note on using the university computer labs** if you are using an official University computer lab computer to access DHBox, aspects of the University's security system might block the RStudio aspect. I am working on a solution to this problem. If you know that you are going to have to use Carleton computers, get in touch right away.

## Some Readings To Kick Things Off

What is digital history anyway? How is it connected to so-called 'big data'? Read the following pieces. Annotate with Hypothes.is anything that strikes you as interesting; annotate anything that puzzles you - feel free to just say, 'I'm not sure what this means; does it mean.... does anybody have any ideas?' **and** if you see someone is asking questions, you can reply to that annotation with thoughts of your own!

**NB** each week, I expect you to respond to at least someone else's annotation in a **substantive** way. No "I agree!" or "right on!" or that sort of thing. Make a **meaningful** contribution.

Once you have read and annotated the works, **write a post on your blog that poses the question 'what is digital history for me anyway?'** . Explain why you're in this class, your level of comfort with digital tech, the kinds of history you're interested in, and what you hope to get out of this course. Your post should link to relevant annotations made by you or by your peers. (Every hypothesis annotation has a direct link visible when you click on the 'share' icon for an existing annotation).

> Excerpts from [Chapter 1, the Historian's Macroscope original draft](http://www.themacroscope.org/?page_id=595); read from 'Joys of Big Data' to 'Chapter One Conclusion'. Use Hypothesis to annotate rather than the 'commenting' function on the site.

> James Baker ['The soft digital history that underpins my book' https://cradledincaricature.com/2017/05/24/the-soft-digital-history-that-underpins-my-book/](https://cradledincaricature.com/2017/05/24/the-soft-digital-history-that-underpins-my-book/)

> James Baker ['The hard digital history that underpins my book' https://cradledincaricature.com/2017/06/06/the-hard-digital-history-that-underpins-my-book/](https://cradledincaricature.com/2017/06/06/the-hard-digital-history-that-underpins-my-book/)

> Jo Guldi and David Armitage, ['The History Manifesto: Chapter 4](https://www.cambridge.org/core/books/history-manifesto/big-questions-big-data/F60D7E21EFBD018F5410FB315FBA4590/core-reader)'

> Tim Hitchcock ['Big Data for Dead People' https://historyonics.blogspot.ca/2013/12/big-data-for-dead-people-digital.html](https://historyonics.blogspot.ca/2013/12/big-data-for-dead-people-digital.html)
>
> On Diversity in Digital History [The Macroscope](http://www.themacroscope.org/2.0/diversity-in-digital-history/) Read and follow through the footnotes to at least two more articles

# Acknowledgements

The writing of this workbook took place alongside the writing of my more formal book on [digital methods](http://themacroscope.org) co-authored with the exceptional [Ian Milligan](http://ianmilligan.ca/) and [Scott Weingart](http://scottbot.net/i-am/). I learned far more about doing digital history from them than they ever from me, and someday, I hope to repay the debt. Other folks who've been instrumental in getting this workbook and course off the ground include Melodee Beals, John Bonnett, Chad Gaffield, Tamara Vaughan, the staff of the EDC at Carleton University, [eCampusOntario](http://ecampusontario.org) and of course, the digital history community on Twitter. My thanks to you all.

**This class was first offered in the Winter 2015 semester at Carleton University in Ottawa Canada as HIST3907b. I am grateful to the participants in that class for the feedback and frank discussions of what worked and what didn't. To see the earlier version of the course, please feel free to browse its [github repository](https://github.com/hist3907b-winter2015/)**
