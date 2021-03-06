# Module 1 Exercises

The exercises in this module are designed to give you the necessary skills to engage with the **doing** of digital history. To ensure success in the course, please do make it through Exercises 1 to 3. Exercise 4 is a bit more complex and not mission-critical. Push yourself if you can.

The exercises in this module cover:

+ Writing in Markdown
+ Using the DH Box command line
+ Converting files with the command line
+ Setting up GitHub
+ Interacting with GitHub from the command line

These exercises walk you through the process of using our DH Box, and of keeping notes about what you're doing, and making those notes open on the web. If you run into trouble, **ask for help** in our Slack space. Annotate this page with where things are going wrong for you. Contact Dr. Graham. **You do not have to suffer in silence!** To ask for help when doing this work is not a sign of weakness, but of maturity.

**All 4 exercises are on this page. Remember to scroll!**

-----

## Exercise 1: Learning Markdown syntax with dillinger.io

Have you ever fought with Word or another word processor, trying to get things **just right**? Word processing is a mess. It conflates writing with typesetting and layout. Sometimes, you just want to get the words out. Othertimes, you want to make your writing as accessible as possible... but your intended recipient can't open your file, because they don't use the same word processor. Or perhaps you wrote up some great notes that you'd love to have in a slideshow; but you can't, because copying and pasting preserves a whole lot of extra **gunk** that messes up your materials.

The answer is to separate your **content** from your **tool**.

This is where the [Markdown syntax](https://daringfireball.net/projects/markdown/syntax) shines. Markdown is a syntax for marking semantic elements within a document explicitly, not in some hidden layer. The idea is to identify units that are meaningful to humans, like titles, sections, subsections, footnotes, and illustrations. At the very least, your files will always remain comprehensible to you, even if the editor you are currently using stops working or "goes out of business."

Writing in this way liberates the author from the tool. Markdown can be written in any plain text editor and offers a rich ecosystem of software that can render that text into beautiful looking documents (incidentally, Hypothes.is annotations can be written in Markdown). For this reason, Markdown is currently enjoying a period of growth, not just as as means for writing scholarly papers but as a convention for online editing in general.

Popular general purpose plain text editors include [TextWrangler](https://www.barebones.com/products/textwrangler/), [Sublime](https://www.sublimetext.com/), and [Atom](https://atom.io/) for Mac, [Notepad++](https://notepad-plus-plus.org/) for Windows, as well as [Gedit](https://wiki.gnome.org/Apps/Gedit) and [Kate](https://kate-editor.org/) for Linux. However, there are also editors that specialize in displaying and editing Markdown. 

**NB** A text editor is different from the default notepad app that comes with Windows or Mac. A text editor shows you **exactly** what is in a file, including tags, code, and other 'hidden' markup.

In this exercise, I want you to become familiar with Markdown syntax. Check out [Sarah Simpkin's quick primer on Markdown](http://programminghistorian.org/lessons/getting-started-with-markdown). There are a number of 'flavours' for Markdown, but in essence, they all mimic the kinds of conventions you would see in an email, using asterisks to indicate emphasis and so on.

1. Check out [the Markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).

2. Visit [dillinger.io](http://dillinger.io) in a new browser window. This looks like a word processor. The left side of the screen is where you write, the right side shows you what your text will look like if you converted the text to HTML. Dillinger 'saves' your work in your browser's memory. You can also point it to save to your Dropbox, Google Drive, or GitHub account (under the cogwheel icon).

3. Write a short 200-500 word piece on the most interesting annotation you've seen one of your classmates make. Why is it interesting? Why has it struck you?

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/Gxb88ujao-U?rel=0" title="Learning markdown with dillinger.io" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

4. Grab at least two Creative Commons images and link outwards to four websites that are relevant to your piece. The Creative Commons license allows re-use. Do you know how to [find Creative Commons images](https://search.creativecommons.org/)?

5. Make sure you link to the annotation in question.

6. Make sure to add the file type `.md` at the end, in the 'document name' slot.

7. Select 'Export to' Markdown to save a copy of the file in your downloads folder.

8. Try 'exporting to' PDF or HTML. Since you've separated the content from the format, this illustrates how you can convert your text into other formats as necessary. (The text is converted using a piece of software called [Pandoc](http://www.pandoc.org/installing.html)).

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/ip7HFi8zozY?rel=0" title="Inserting images and exporting in dillinger.io" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

See how easy that was? Don't worry about submitting this.... yet.

**NB** The next time you go to dillinger.io the last document you were working on will load up. That's because dillinger stashes your work in the browser cache. If you clear your cache (from your browser's tools or settings) you'll lose it, which is why in step 7 I suggested exporting.

For a richer discussion of some more ways Markdown and Pandoc can make your research sustainable, see Tenen and Wythoff, [Sustainable Authorship in Plain Text Using Pandoc and Markdown](http://programminghistorian.org/lessons/sustainable-authorship-in-plain-text-using-pandoc-and-markdown).

-----

## Exercise 2: Getting familiar with DH Box

### Setting up DH Box

Many of the exercises in this workbook work without issue on a Mac or Linux computer, at the terminal. (On a Mac, you can find the Terminal under Applications > Utilities). If you're on a Windows machine, it can be more difficult to get all of the various bits and pieces properly configured. If you're on a tablet, most digital history things you might like to do are not really feasible. One solution is for all of us to use the **same** computer. The CUNY Graduate Centre has created a digital-humanities focused virtual computer for just such an occasion, the [DH Box](http://dhbox.org/).

In this exercise, you are going to set up an instance of a DH Box for your own use. We will be using the command line interface which is an essential way to interact with your computer. Normally, when you're on your Mac or your PC, you're clicking on icons or menus or windows of various sorts to get things done. You're clicking and dragging text. All of these graphical elements sit on top of sequences of commands that you don't have to type out, that only the computer sees. The command line (i.e. terminal or command prompt) lets you dispense with the graphical elements, and type the commands you want directly. 

**NB This workbook assumes that you are using a DH Box**

1. Carleton students: If you are on campus or are logged into Carleton's systems via a VPN, go to [the sign up page at http://134.117.26.132:5000/signup](http://134.117.26.132:5000/signup). Other folks: Go to [the DH Box sign up page at http://dhbox.org/signup](http://dhbox.org/signup). These are two separate installations of DH Box; whichever one you start with, continue to use.

2. Select a username, password, and your email address. Your username must be four characters or longer. 

3. Select '1 month'. Then select launch. You now have a virtual computer that you can use for the next month. Whenever you come back to the DH Box, you can now click 'login' on your personal DH computer and your work will be there waiting for you. Once you've logged in, the site will reload to the DH Box welcome screen, but your user name will show at the top right.

4. Click on your username, and there will be a new option, **Apps.** Click here to go into your DH Box.

Inside the DH Box, you can click on:

+ **Home:** tells you how many days until your DH Box expires. Keep an eye on this, as you'll want to get your materials out of DH Box before that happens.
+ **File Manager:** allows you to view all of your files, as well as uploading/downloading materials from DH Box to your local computer.
+ **Command Line:** allows you to interact with the computer at the terminal prompt or command line &mdash; this is where you type in commands to your machine.
+ **RStudio:** is an environment for doing statistical computing.
+ **Brackets:** is a text editor for web development.
+ **Jupyter Notebooks:** is an environment for creating documents that have running code inside of them.

For HIST3814o, we will use the **File Manager**, the **Command Line**, and **RStudio.**

### Using the Command Line 

In the previous exercise, [dillinger.io](http://dillinger.io) could convert your Markdown document into HTML or PDF. We will now add the Pandoc program to DH Box so that you can convert things for yourself. We will get the Pandoc program and bring it into our DH Box using the `wget` command. Wget is a program that allows us to download materials off the web. It can be used to only grab certain file types, or all files within a certain directory, or even to take a complete copy of a website! We'll discuss wget more in [Module 2](../module-2/Exercises/#exercise-2-wget) (visit also [the Programming Historian on wget](http://programminghistorian.org/lessons/automated-downloading-with-wget)).

1. Select Command Line in your DH Box. You will have to login again with your DH Box username and password. 

    **NB In many tutorials or how-tos, you will see the `$` sign at the beginning of some text you are meant to type. This is a convention to show that what follows the `$` is to be typed at the command prompt.**

    For example, when you type or copy the command

    `$ wget https://github.com/jgm/pandoc/releases/download/1.19.2.1/pandoc-1.19.2.1-1-amd64.deb`

    you omit the `$` and type or copy just the command

    `wget https://github.com/jgm/pandoc/releases/download/1.19.2.1/pandoc-1.19.2.1-1-amd64.deb`

2. Type `$ wget https://github.com/jgm/pandoc/releases/download/1.19.2.1/pandoc-1.19.2.1-1-amd64.deb`

    This wget command gets a copy of the Pandoc program that will work in DH Box. The `.deb` file extension tells us that this is a Linux file. The next step is to unpack that file.

3. Type `$ sudo dpkg -i pandoc-1.19.2.1-1-amd64.deb`

    Some commands can have nasty side effects, and the operating system won't let you do them unless you specify that you **really** want to do them. That's what the [sudo command](https://en.wikipedia.org/wiki/Sudo) achieves. The next part, `
    dpkg` with the `-i` 'flag' is a 'package manager' for installing software. The last part is the file that we used wget to copy to our own machine. 

4. Type `$ pandoc -v` to test that Pandoc is installed

    If all has gone well, DH Box will tell you what version of Pandoc you have installed, who it was built by, and a copyright notice.

5. Type `$ history`

    This creates a file to keep a record of what commands we have been typing.

    DH Box returns a list of every command that you've typed. 

6. Type `$ history > dhbox-work-today.md`

    This will **pipe** that information into a new file.

    When you hit enter, the computer seems to pause for a moment, and then it shows you the command prompt again. How do we know if anything happened? Generally, when working at the command prompt, no news is good news. There are two ways you can check to see if the new file `dhbox-work-today.md` was created. **You can click on the File Manager** (the first folder will have your username; click on that, and then you'll see a list of files) and there it is! **Click on the file name,** and it will download to your computer where you can open it with a text editor.

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/bsTZC8jtt4M?rel=0" title="Using the command line: wget and installing programs" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

    Alterntively, type `$ ls`

    This **lists** &mdash; ls &mdash; all the files in the directory. How do you know what directory you're in? You can use the `pwd` command, which prints the working directory.

    Let's take a look inside that new file you created. There is a text editor that you can use, called **Nano**. 

7. Type `$ nano dhbox-work-today.md`

    This opens the text editor, and you can see that the history command has copied its output into the editor. **If you got an error:** Sometimes, tools or commands we want to use are not present in the system. DH Box uses the **Ubuntu** operating system (an operating system is the underlying code that makes a PC a PC, a Mac a Mac, etc). We can install all sorts of useful things by using the `apt-get` command. **To get and install Nano, try re-installing Nano with the following command:**

    `$ sudo apt-get install nano`.

    The computer makes things a little more difficult sometimes when you're asking it to do something that changes or adds capabilities. Simply typing `apt-get` wouldn't work. `sudo` tells the computer that I **really** do want to execute the command (it stands for 'super-user do'). Any `sudo` command will make the computer ask for your password to confirm that you really do want to run that command.

    [Read the beginner guide for the Nano text editor on How to Geek now](https://www.howtogeek.com/howto/42980/the-beginners-guide-to-nano-the-linux-command-line-text-editor/).

8. In Nano, with your file open, make a header (remember to use `#` to indicate a header) at the start of the file which has today's date in it, and add some text explaining what you're trying to do with this exercise. 

9. Hit ctrl+x to exit Nano.

10. Nano will ask you if you want to 'Save modified buffer?'. **Hit `y`, then when it asks you for the file name, hit enter.**

    The entire key sequence for saving and exiting Nano is **ctrl-x, y, enter**.

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/JVjStzebni8?rel=0" title="Using the command line: editing files with nano" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

11. Use the File Manager to save a copy of `dhbox-work-today.md` onto your own computer.

    One last thing: let's convert the Markdown file into both Word and HTML. Pandoc is capable of quite sophisticated transformations, but these are two of the easiest. 

12. Type `$ pandoc -o todayscommands.docx dhbox-work-today.md`

    This says to Pandoc, create an output file ( the `-o`) called `todayscommands.docx` from `dhbox-work-today.md`. 

13. Type `$ ls` after running this command to see if you've made the file. 

    Any guesses how to create an HTML file? Pandoc is smart enough to know the kind of output you want from the file extension.

14. Retype the command but use `.html` instead of `.docx` this time. Use the file manager to save copies of the `.docx` and `.html` files to your own machine. (Incidentally, if you use the arrow up and arrow down keys on your keyboard when you're at the command line, you can page through commands that you've previously typed).

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/CZgJLys2RvU?rel=0" title="Using the command line: converting files with pandoc" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

You've done some interesting work &mdash; you've installed software into a remote computer, you've copied all of the commands you typed into a new file, you've used Markdown and a text editor to add information and context to those commands, and you've used Pandoc to transform your basic text into the more complicated formats of Word or HTML.

As you do more work in this workbook, I want you to get in the habit of keeping these copies of what you've done. These are your actual lab notes, and they are invaluable for helping you keep track of what you've been doing and what you've been trying. If you remember the course manual, keeping a lab notebook is part of the assessment of the course.

In the next exercise, we learn to use another piece of software called 'git' which will enable you to set up a remote location for pushing copies of your work to, for safe keeping and for collaboration. For more on why we go to all this trouble, visit the Programming Historian on ['Preserving Your Research Data'](http://programminghistorian.org/lessons/preserving-your-research-data).

Visit [Ubuntu's handy cheat-sheet of keyboard shortcuts and other useful commands](https://help.ubuntu.com/community/AdvancedCommandlineHowto#Keyboard_shortcuts) for your DH Box command-line work.

-----

## Exercise 3: Setting up your GitHub space

It's a familiar situation &mdash; you've been working on a paper. It's where you want it to be, and you're certain you're done. You save it as `final.doc`. Then, you ask your friend to take a look at it. She spots several typos and that you flubbed an entire paragraph. You open it up, make the changes, and save as `final-w-changes.doc`. Later that day it occurs to you that you don't like those changes, and you go back to the original `final.doc`, make some changes, and just overwrite the previous version. 

Soon, you have a folder resembling the following:

```
|-project
    |-'finalfinal.doc'
    |-'final-w-changes.doc'
    |-'final-w-changes2.doc'
    |-'isthisone-changes.doc'
    |-'this.doc'
```

Things can get messy quite quickly. Imagine that you also have several spreadsheets in there as well, images, snippets of code... we don't want this. What we want is a way of managing the evolution of your files. We do this with a program called [git](https://git-scm.com/). Git is not a user-friendly piece of software, and it takes some work to get your head around. Git is also very powerful, but fortunately, the basic uses to which most of us put it to are more or less straightforward. There are many other programs that make use of git for version control; these programs weld a graphical user interface on top of the main git program. For now, we'll content ourselves with the [GitHub website](http://github.com), which does the same thing more or less, but from a browser.

Firstly, let's define some terms.

+ **git** is a program that keeps snapshots of the contents of a designated folder; it watches for 'difs' or differences between one snapshot and the next. You 'commit' these snapshots to a repository, which lives on your computer (it's just a folder).
+ **GitHub** is a webservice that allows you to share those repositories, and to keep track of those **versions** online, and what's more, to share the repositories and files with multiple collaborators, and **keep everyone's changes straight!** There are other services that work like GitHub, such as [Bitbucket](https://bitbucket.org/). GitHub is just one of the better known services. You can browse GitHub repositories for code that solves a particular problem for you, software, and data.

**NB Because we are going to use the free version, we cannot make the repositories we create private.**

In this exercise, we're going to create a repository via the GitHub website and use it as a kind of back-up space for the files you created in the previous exercise. In the follow up exercise, you will learn how to do this from the command line.

1. Go to [GitHub](http://github.com) and sign up for an account. Remember, you don't have to use your real name. If you use a pseudonym, please communicate to me privately what your account is called.

2. Once you're logged in, we will create a new repository called `hist3814o`. Click on the `+` at the top right of the screen, beside your avatar image.

3. Write a short description in the 'description box', and tick off the 'initialize the repository with a readme'. You can also select a license from the drop down box &mdash; this will put some standard wording on your repository page about the conditions under which someone else might use (or cite) your code.

4. Click 'Create repository'.

    At this point, you now have a folder &mdash; a repository &mdash; on the GitHub website into which you can deposit your files. It will be at `http://github.com/your-account-name/hist3814o`. So let's put some materials into that repository.

    Notice, when you're on your repository's page, that there is a button to 'create new file' and another for 'upload files'.

5. Click on upload files.

6. Drag the HTML file you created in the previous exercise (the one you made with Pandoc, and then saved to your computer via the DH Box File Manager) into the large grey box. This will upload the file. You can drag multiple files into the box to upload them into your repository. 

7. Enter a brief commit message in the commit message box. Then hit the green commit changes button. Git &mdash; and GitHub &mdash; attach messages to any 'commits' you make. These messages are brief notes explaining why you were making the commit. This way, if you ever had to roll back (go back to an earlier version) you can understand the evolution of the repository and find the spot you want. 

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/ysOdMJOd3Bo?rel=0" title="Setting up your Github space" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

Instead of creating multiple versions of a file, you have a single file that has a version history. Neat, eh?

This is perhaps the simplest use case for GitHub. You can create files directly in the repository as well, by hitting the 'create new file' button, and following the prompts. GitHub has a [brief tutorial on using the website to collaborate with other people on a repository](https://guides.github.com/activities/hello-world/).

**For the remainder of the course, use your hist3814o repository as your scratch pad, your fail log, and your open notebook for showing your work across these modules**.

Check out [my example 'fail log' as a model](https://github.com/shawngraham/example-faillog-hist3814). 'Fail' is a pretty harsh word &mdash; I use it to point out that for everything that works perfectly, there's an awful lot of trial-and-error that happened first **upon which** our successes are built. We need to keep track of this! James Baker calls this, **[de-wizardification](https://cradledincaricature.com/2017/06/29/dewizardification/).**

Some useful vocabulary when discussing git, GitHub, and version control:

+ `repository` a single folder that holds all of the files and subfolders of your project.
+ `commit` this means, 'take a snapshot of the current state of my repository'.
+ `publish` take a folder on my computer, and copy it and its contents to the web as a repository at `github.com/myusername/repositoryname`.
+ `sync` update the web repository with the latest commit from the folder on my computer.
+ `branch` make a copy of my repository with a 'working name'.
+ `merge` fold the changes I have made on a branch into another branch (typically, either `master` or `gh-pages`).
+ `fork` to make a copy of someone else's repo.
+ `clone` to copy a repo online onto your own computer.
+ `pull` request to ask the original maker of a repo to 'pull' your changes into their master, original, repository.
+ `push` to move your changes from your computer to the online repo.

### An aside

Many websites &mdash; including this workbook &mdash; use a GitHub repository as a way of hosting a website. The video below by historian Jack Dougherty shows how this could be done. Note that the HTML code that he pastes into an `index.html` file (the first page of any website is usually called `index.html`) he got from a different service. You could write a document in Markdown, then use Pandoc to convert that into an `index.html`, for example.

<iframe width="560" height="315" src="https://www.youtube.com/embed/ZVejLE8qtOI?rel=0" title="GitHub Pages Tutorial" frameborder="0" allowfullscreen></iframe>

-----

## Exercise 4: A detailed look at using git on the command line

At its heart, git is a way of taking 'snapshots' of the current state of a folder, and saving those snapshots in sequence. (For an excellent brief presentation on git, visit [Alice Bartlett's presentation on the subject](https://speakerdeck.com/alicebartlett/git-for-humans); Bartlett is a senior developer for the Financial Times). In git's lingo, as stated earlier, a folder on your computer is known as a repository or repo. This sequence of snapshots in total lets you see how your project unfolded over time. Each time you wish to take a snapshot, you make a `commit`. A commit is a git command to take a snapshot of the entire repository. Thus, your folder we discussed above, with its proliferation of documents becomes:

```
|-project
    |-'final.doc'
```    

**But** its commit history could be visualized like a string of pearls, where each pearl is a unique commit. Each one of those pearls represents a point in time when you the writer made a commit; git compared the state of the file to the earlier state, and saved a snapshot of the **differences**. What is particularly useful about making a commit is that git requires two more pieces of information about the git: who is making it, and when. The final useful bit about a commit is that you can save a detailed message about **why** the commit is being made. In our hypothetical situation, your first commit message might look like this:

```
Fixed conclusion

Julie pointed out that I had missed
the critical bit in the assignment
regarding stratigraphy. This was
added in the concluding section.
```

This information is stored in the history of the commits. In this way, you can see exactly how the project evolved and why. Each one of these commits has what is called a `hash`. This is a unique fingerprint that you can use to 'time travel' (in Bartlett's felicitous phrasing). If you want to see what your project looked like a few months ago, you `checkout` that commit. This has the effect of 'rewinding' the project. Once you've checked out a commit, don't be alarmed when you look at the folder: your folder (your repository) looks like how it once did all those weeks ago! Any files written after that commit seem as if they've disappeared. Don't worry, they still exist!

What would happen if you wanted to experiment or take your project in a new direction from that point forward? Git lets you do this. What you will do is create a new `branch` of your project from that point. You can think of a branch as like the branch of a tree, or perhaps better, a branch of a river that eventually merges back to the source. (Another way of thinking about branches is that it is a label that sticks with these particular commits.) 

It is generally considered **best practice** to leave your `master` branch alone, in the sense that it represents the best version of your project. When you want to experiment or do something new, you create a `branch` and work there. If the work on the branch ultimately proves fruitless, you can discard it. **But**, if you decide that you like how it's going, you can `merge` that branch back into your master. A merge is a commit that folds all of the commits from the branch with the commits from the master.

Git is also a powerful tool for backing up your work. You can work quite happily with git on your own machine, but when you store those files and the history of commits somewhere remote, you open up the possibility of collaboration **and** a safe place where your materials can be recalled if &mdash; perish the thought &mdash; something happened to your computer. In git-speak, the remote location is, well, the `remote`. There are many different places on the web that can function as a remote for git repositories. You can even set one up on your own server, if you want. To get material **out** of GitHub and onto your own computer, you `clone` it. If that hypothetical paper you were writing was part of a group project, your partners could clone it from your GitHub space, and work on it as well!

Let us imagine a scenario.... You and Anna are working together on the project. You have made a new project repository in your GitHub space, and you have cloned it to your computer. Anna has cloned it to hers. Let's assume that you have a very productive weekend and you make some real headway on the project. You `commit` your changes, and then `push` them from your computer to the GitHub version of your repository. That repository is now one commit **ahead** of Anna's version. Anna `pulls` those changes from GitHub to her own version of the repository, which now looks **exactly** like your version. What happens if you make changes to the exact same part of the exact same file? This is called a **conflict**. Git will make a version of the file that contains text clearly marking off the part of the file where the conflict occurs, with the conflicting information marked out as well. The way to **resolve** the conflict is to open the file (typically with a text editor) and to delete the added git text, making a decision on which information is the correct information.

**Caution** What follows might take a bit of time. It walks you through setting up a git repository in your DH Box; making changes to it; making different branches; and publishing the repository to your space on GitHub's website.

### 4.1. git init 

How do you turn a folder into a repository? With the `git init` command. At the command line (remember, the `$` just shows you the prompt; you don't have to type it!):

1. Type `$ mkdir first-repo` to make a new directory.
2. Type `$ ls` (list) to see that the directory exists. Then change directory into it: `cd first-repo`. (Remember: if you're ever not sure what directory you're in, type `$ pwd`, or print working directory.)
3. Make a new file called `readme.md`. You do this by calling the text editor: `nano readme.md`. 
4. Type an explanation of what this exercise is about. 
5. Hit ctrl+x to exit, then type y to save, leave the file name as it is. Hit enter. **If you get an error to the effect that Nano is not found** you just need to install it with `$ sudo apt-get install nano`. DH Box will ask you for your password again. Once the dust settles, you can make the new file with `$ nano readme.md`.
6. Type `$ ls` again to check that the file is there.
7. Type `$ git init` to tell the git program that this folder is to be tracked as a repository. If all goes correctly, you should see a variation on this message: `Initialized empty Git repository in /home/demonstration/first-repo/.git/`.
8. Type `$ ls` again. What do you (not) see?

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/xboW84JJaX0?rel=0" title="Initializing a repository with git" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

The changes in your repo will now be stored in that **hidden** directory, `.git`. Most of the time, you will never have reason to search that folder out. But know that the config file that describes your repo is in that folder. There might come a time in the future where you want to alter some of the default behaviour of the git program. You do that by opening the config file (which you can read with a text editor). Google 'show hidden files and folders' for your operating system when that time comes.

### 4.2. git status
Open your `readme.md` file again with the Nano text editor, from the command line. Add some more information to it, then save and exit the text editor.

1. Type `$ git status`

    Git will respond with a couple of pieces of information. It will tell you which `branch` you are on. It will list any untracked files present or new changes that are unstaged. 

2. We now will `stage` those changes to be added to our commit history by typing `$ git add -A`. (the bit that says `-A` adds any new, modified, or deleted files to your commit when you make it. There are [other options or flags](https://stackoverflow.com/questions/572549/difference-between-git-add-a-and-git-add#572660) where you add **only** the new and modified files, **or** only the modified and deleted files.)

3. Let's check our git status again: type `$ git status`

4. You should see something like this:

        On branch master
        Initial commit
        Changes to be committed:
          (use "git rm --cached <file>..." to unstage)
                new file:   readme.md

5. Let's take a snapshot: type `$ git commit -m "My first commit"`. This command represents a bit of a shortcut for making commit messages by using the `-m` flag to associate the text in the quotation marks with the commit. 

    What happened? Remember, git keeps track not only of the changes, but **who** is making them. If this is your first time working with git in the DH Box, git will ask you for your name and email. 

6. Helpfully, the Git error message tells you exactly what to do: type `$ git config --global user.email "you\@example.com"` and then type `$ git config --global user.name "Your Name"`. Now try making your first commit.

7. Open up your `readme.md` file again, and add some more text to it. 

8. Save `readme.md` and exit the text editor. 

9. Add the new changes to the snapshot that we will take.

10. Type `$ git commit`. Git automatically opens up the text editor so you can type a longer, more substantive commit message. In this message (unlike in Markdown) the `#` indicates a line to be ignored. You'll see that there is already some default text in there telling you what to do. 

11. Type a message indicating the nature of the changes you have made. 

12. Save and exit the text editor. **DO NOT** change the filename!

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/EK0lZiIj00w?rel=0" title="Checking our repository with git status" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

Congratulations, you are now able to track your changes, and keep your materials under version control!

### 4.3. git merge

Go ahead and make some more changes to your repository. Add some new files. Commit your changes after each new file is created. 

Now we're going to view the history of your commits. 

1. Type `$ git log`. What do you notice about this list of changes? Look at the time stamps. You'll see that the entries are listed in reverse chronological order. Each entry has its own 'hash' or unique ID, the person who made the commit and time are listed, as well as the commit message eg:

        commit 253506bc23070753c123accbe7c495af0e8b5a43
        Author: Shawn Graham <shawn.graham@carleton.ca>
        Date:   Tue Feb 14 18:42:31 2017 +0000

        Fixed the headings that were broken in the about section of readme.md

2. We're going to go back in time and create a new branch. You can escape the `git log` by typing `q`. Here's how the command will look: `$ git checkout -b branchname <commit>` where `branch` is the name you want the branch to be called, and `<commit>` is that unique ID. Make a new branch from your second last commit (don't use the `<` or `>` symbols).
3. We typed `git checkout -b experiment 253506bc23070753c123accbe7c495af0e8b5a43`. The response: `Switched to a new branch 'experiment'` 
4. Check git status and then list the contents of your repository. What do you see? You should notice that some of the files you had created before seem to have disappeared &mdash; congratulations, you've time travelled! Those files are not missing; but they **are** on a different branch (the master branch) and you can't harm them now. 
5. Add a number of new files, making commits after each one. 
6. Check your git status, and check your git log as you go to make sure you're getting everything. Make sure there are no unstaged changes &mdash; everything's been committed.

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/iKNNwuiMhOc?rel=0" title="Merging repository branches with git merge" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

### 4.4. git merge continued

Now let's assume that your `experiment` branch was successful &mdash; everything you did there you were happy with and you want to integrate all of those changes back into your `master` branch. We're going to merge things. To merge, we have to go back to the master branch: `$ git checkout master`. (Good practice is to keep separate branches for all major experiments or directions you go. In case you lose track of the names of the branches you've created, this command: `git branch -va` will list them for you.)

1. Now, we merge with `$ git merge experiment`. Remember, a merge is a special kind of commit that rolls all previous commits from both branches into one &mdash; git will open your text editor and prompt you to add a message (it will have a default message already there if you want it). 
2. Save and exit and ta da! Your changes have been merged together.

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/yeXpmvr5yzI?rel=0" title="Merging repository branches with git merge continued" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

### 4.5 git push

One of the most powerful aspects of using git is the possibility of using it to manage collaborations. To do this, we have to make a copy of your repository available to others as a `remote`. There are a variety of places on the web where this can be done; one of the most popular at the moment is [GitHub](http://github.com). GitHub allows a user to have an unlimited number of public repositories. **Public** repositories can be viewed and copied by anyone. **Private** repositories require a paid account, and access is controlled. If you are working on sensitive materials that can only be shared amongst the collaborators on a project, you should invest in an upgraded account (note that you can also control which files get included in commit; [visit GitHub for help on ignoring files](https://help.github.com/articles/ignoring-files/). In essence, you simply list the file names you do not want committed; [visit GitHub for an example on listing ignored files](https://gist.github.com/octocat/9257657)). **Let's assume that your materials are not sensitive**.

1. Login to GitHub.

2. On the upper right part of the screen there is a large + sign. Click on that + sign, and select `new repository`.

3. On the following screen, give your repo a name.

4. Leave the repository set to 'Public'.

5. **DO NOT** 'initialize this repo with a readme.md'. Leave `add .gitignore` and `add license` set to NONE.

6. Click the green 'Create Repository' button. You now have a space into which you will publish the repository on your machine. 

7. At the command line, we now need to tell git the location of this space. We do that with the following command, where you will change `your-username` and `your-new-repo` appropriately:

        $ git remote add origin https://github.com/YOUR-USERNAME/YOUR-NEW-REPO.git

8. Now we push your local copy of the repository onto the web, to the GitHub version of your repo:

        $ git push -u origin master

    **NB If you wanted to push a `branch` to your repository on the web instead, do you see how you would do that? If your branch was called `experiment`, the command would look like this:**

        $ git push origin experiment

    The changes can sometimes take a few minutes to show up on the website. Now, the next time you make changes to this repository, you can push them to your GitHub account &mdash; which is the 'origin' in the command above.  

9. Add a new text file. Commit the changes. Push the changes to your account.

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/1CFdmsPPJaU?rel=0" title="Updating your repository with git push" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

### 4.6. git clone

Imagine you are collaborating with one of your classmates. Your classmate is in charge of the project, and is keeping track of the 'official' folder of materials (i.e. the repo). You wish to make some changes to the files in that repository. You can manage that collaboration via GitHub by making a copy, what GitHub calls a `fork`.

1. Make sure you're logged into your GitHub account on the GitHub website. We're going to fork an example repository right now by going to [GitHub's forking example page](https://github.com/octocat/Spoon-Knife). 

2. Click the 'fork' button at top-right. GitHub now makes a copy of the repository in your own GitHub account!

3. To make a copy of that repository on your own machine, you will now clone it with the `git clone` command. (Remember: a 'fork' copies someone's GitHub repo into a repo in your OWN GitHub account; a 'clone' makes a copy on your own MACHINE). Type:

        $ cd..
        $ pwd

4. We do that to make sure you're not **inside** any other repo you've made! Make sure you're not inside the repository we used in Exercises 1 to 4, then proceed:

        $ git clone https://github.com/YOUR-USERNAME/Spoon-Knife.git
        $ ls

    You now have a folder called 'Spoon-Knife' on your machine! Any changes you make inside that folder can be tracked with commits. You can also `git push -u origin master` when you're inside it, and the changes will show up on your OWN copy (your fork) on `github.com`.

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/LaPXfNx35Vg?rel=0" title="Cloning another repository with git clone" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

5. Make a fork of, and then clone, one of your classmates' repositories. Create a new branch. Add a new file to the repository on your machine, and then push it to your fork on GitHub. Remember, your new file will appear on the new branch you created, NOT the master branch.

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/8xHO6blhUZU?rel=0" title="Merging repositories with git merge" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

### 4.7. pull request

Now, you let your collaborator know that you've made a change that you want her to `merge` into the original repository. You do this by issuing a `pull request`. But first, we have to tell git to keep an eye on that original repository, which we will call `upstream`. You do this by adding that repository's location like so:

1. Type (but change the address appropriately):

        $ git remote add upstream THE-FULL-URL-TO-THEIR-REPO-ENDING-WITH-.git

2. You can keep your version of the remote up-to-date by fetching any new changes your classmate has done:

        $ git fetch upstream


    Now let's make a `pull` request (you might want to [bookmark GitHub's help document for pull requests](https://help.github.com/articles/creating-a-pull-request/)). 

3. Go to your copy of your classmate's repository at your GitHub account. Make sure you've selected the correct branch you pushed your changes to, by selecting it from the Branches menu drop down list.

4. Click the 'new pull request' button.

5. The new page that appears can be confusing, but it is trying to double check with you which changes you want to make, and where. Make sure these are set properly.

    + **Base branch** is the branch where you want your changes to go (ie. your classmate's repository). 

    + **Head branch** is the branch where you made **your** changes. 

    Remember: the **Base** branch is the **TO**, the **Head** branch is the **FROM** &mdash; the place where you want your changes to go **TO**, **FROM** the place where you made the changes. 

    For example, say I clone Dr. Graham's `R` repository and create a new `experiment` branch: 
        
    + If I make changes to my `experiment` branch &mdash; that is the **Head** branch. 
    + Then I push those changes to Dr. Graham's `master` branch &mdash; that is the **Base** branch.

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/PuqWBWbjptA?rel=0" title="Preparing your changes to a repository for a pull request" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

6. A pull request has to have a message attached to it, so that your classmate knows what kind of change you're proposing. Fill in the message fields appropriately, then hit the 'create pull request' button.

    <br>
    <iframe width="560" height="315" src="https://www.youtube.com/embed/HFDtkJ4OLSI?rel=0" title="Making a pull request on a friend's respository" frameborder="0" gesture="media" allowfullscreen></iframe>
    <br>

### 4.8. git merge again

Finally, the last bit of work to be done is to accept the pull request and `merge` the changes into the original repository.

1. Go to your repository on your GitHub account. Check to see if there are any 'pull requests' &mdash; these will be listed under the 'pull requests' tab. Click on that tab.
2. You can merge from the command line, but for now, you can simply click on the green 'merge pull request' button, and then the 'confirm merge' button. The changes your classmate has made have now been folded into your repository.
3. To get the updates on your local machine, go back to the command line and type

          $ git pull origin master


Phew. You might want to do `$ history > recentcommands.md` just to remember what you've done. And then commit that to a repository.

-----

## Conclusion

In the modules to come, we will be using DH Box as we find data, fetch data, wrangle data, analyze data, and visualize data. It becomes very important that you note the kinds of commands you use or try, the thinking that you were doing at that point, and so on. You want to leave yourself (and anybody who comes after) breadcrumbs so that you understand what you were doing. Quick notes written in Markdown, piping the history of what you've done to a file, and keeping those files in a repository alongside any other code or files that you may make will set you on the path to open access research and computational reproducibility. As Martha might say, 'and that's a good thing'.
