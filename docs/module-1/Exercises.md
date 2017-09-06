# Module 1: Exercises

The exercises are designed to give you the necessary skills to engage with the doing of digital history. To ensure success in the course, please do make it through exercises 1 - 3. Exercise 4 is a bit more complex and not mission-critical. Push yourself if you can.

These exercises walk you through the process of using our DHBox, and of keeping notes about what you're doing, and making those notes open on the web. If you run into trouble, **ask for help** in our Slack space. Annotate this page with where things are going wrong for you. Contact Dr. Graham. _You do not have to suffer in silence!_ To ask for help when doing this work is not a sign of weakness, but of maturity.

_All 4 exercises are on this page. Remember to scroll!_

## EXERCISE 1: learning markdown syntax with dillinger.io

Have you ever fought with Word or another wordprocessor, trying to get things just _right_? Word processing is a mess. It conflates writing with typesetting and layout. Sometimes, you just want to get the words out. Othertimes, you want to make your writing as accessible as possible... but your intended recipient can't open your file, because they don't use the same wordprocessor. Or perhaps you wrote up some great notes that you'd love to have in a slideshow; but you can't, because copying and pasting preserves a whole lot of extra _gunk_ that messes up your materials.

The answer is to separate your _content_ from your tool.

This is where the [Markdown syntax](https://daringfireball.net/projects/markdown/syntax) shines. Markdown is a syntax for marking semantic elements within a document explicitly, not in some hidden layer. The idea is to identify units that are meaningful to humans, like titles, sections, subsections, footnotes, and illustrations. At the very least, your files will always remain comprehensible to you, even if the editor you are currently using stops working or "goes out of business."

Writing in this way liberates the author from the tool. Markdown can be written in any plain text editor and offers a rich ecosystem of software that can render that text into beautiful looking documents (incidentally, Hypothes.is annotations can be written in Markdown). For this reason, Markdown is currently enjoying a period of growth, not just as as means for writing scholarly papers but as a convention for online editing in general.

Popular general purpose plain text editors include TextWrangler and Sublime for Mac, Notepad++ for Windows, as well as Gedit and Kate for Linux. However, there are also editors that specialize in displaying and editing Markdown. **nb** a text editor is different from the default notepad app that comes with Windows or Mac. A text editor shows you *exactly* what is in a file.

In this exercise, I want you to become familiar with Markdown syntax ([here is a quick primer on markdown by Sarah Simpkin](http://programminghistorian.org/lessons/getting-started-with-markdown)). There are a number of 'flavours' for Markdown, but in essence, they all mimic the kinds of conventions you would see in an email, using asterisks to indicate emphasis and so on.

1. You will need [the markdown cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).
2. Go to [dillinger.io](http://dillinger.io) in a new browser window. This looks like a wordprocessor. The left hand side of the screen is where you write, the right hand side shows you what your text will look like *if you converted the text to html*. Dillinger 'saves' your work in your browser's memory. You can also point it to save to your dropbox, google drive, or github account (under the cogwheel icon).
3. Write a short 200-500 word piece on the most interesting annotation you've seen one of your classmates make. Why is it interesting? Why has it struck you?
4. Have at least two images (creative commons licensed for re-use - do you know how to [find creative commons images](https://search.creativecommons.org/)?) and link outwards to four websites that are relevant to your piece.
5. Make sure you link to the annotation in question.
6. In the 'document name' slot, make sure to add the file type .md at the end
7. 'Export to' markdown to save a copy of the file in your downloads folder.
8. Try 'exporting to' pdf or html. Since you've separated the content from the format, this illustrates how you can transform your text into other formats as necessary. (The converter is a piece of software called [pandoc](http://www.pandoc.org/installing.html))

See how easy that was? Don't worry about submitting this.... yet.

> nb: the next time you go to dillinger.io the last document you were working on will load up. That's because dillinger stashes your work in the browser cache. If you clear your cache (from your browser's tools or settings) you'll lose it, which is why in step 7 I suggested exporting..

(For a richer discussion of some more ways markdown and pandoc can make your research sustainable, see Tenen and Wythoff, [Sustainable Authorship in Plain Text Using Pandoc and Markdown](http://programminghistorian.org/lessons/sustainable-authorship-in-plain-text-using-pandoc-and-markdown))

## EXERCISE 2: Getting familiar with DHBox

Many of the exercises in this workbook work without issue on a Mac or Linux computer, at the terminal. (On a Mac, you can find the terminal under applications > utilities). If you're on a Windows machine, it can be more difficult to get all of the various bits and pieces properly configured. If you're on a tablet, most digital history things you might like to do are not really feasible. One solution is for all of us to use the _same_ computer. The CUNY Graduate Centre has created a digital-humanities focused virtual computer for just such an occasion.

In this exercise, you are going to set up an instance of a DHBox for your own use.

**NB this workbook assumes that you are using a DHBox**

1. Carleton students: If you are on campus or are logged into Carleton's systems via a VPN, go to [http://134.117.26.132:5000/signup](http://134.117.26.132:5000/signup). Other folks: Go to [http://dhbox.org/signup](http://dhbox.org/signup). These are two separate installations of DHBox; whichever one you start with, continue to use.
2. Select a username, password, and your email address. **Your username must be four characters or longer**. Then select '1 month'. Then select launch.

You now have a virtual computer that you can use for the next month.

Whenever you come back to the dhbox, you can now click 'login' and your personal dh computer and your work will be there waiting for you. Once you've logged in, the site will reload to the DHbox welcome screen, but your user name will show at the top right.

+ Click on your username, and there will be a new option, 'apps'. Click here to go into your dhbox.

Inside the DHBox, you can click on 'home', 'file manager', 'command line', 'r studio', 'brackets', 'jupyter notebooks'. The 'home' page will tell you how many days until your dhbox expires. Keep an eye on this, as you'll want to get your materials out of dhbox before that happens. 'File manager' allows you to view all of your files, as well as uploading/downloading materials from dhbox to your local computer. 'Command line' allows you to interact with the computer at the terminal prompt or command line - this is where you type in commands to your machine. 'R Studio' is an environment for doing statistical computing, 'Brackets' is for web development, and 'Jupyter Notebooks' is an environment for creating documents that have running code inside of them. For HIST3814o, we will use the file manager, the command line, and R studio

In the previous exercise, [Dillinger.io](http://dillinger.io) could convert your markdown document into html or pdf. We will now add the pandoc program to DHBox so that you can convert things for yourself. We will get the Pandoc program and bring it into our DHBox using the `wget` command. Wget is a program that allows us to download materials off the web. It can be used to only grab certain file types, or all files within a certain directory, or even to take a compete copy of a website! We'll discuss wget more in module 2 (see also [the Programming Historian](http://programminghistorian.org/lessons/automated-downloading-with-wget)).

For now, select 'command line' in your dhbox. You will have to login again with your dhbox username and password. In many tutorials or how-tos, you will see the `$` sign at the beginning of some text you are meant to type. This is a convention to show that what follows the $ is to be typed at the command prompt.

`$ wget https://github.com/jgm/pandoc/releases/download/1.19.2.1/pandoc-1.19.2.1-1-amd64.deb`

...so don't type the $, but rather, type the wget etc.

This command gets a copy of the Pandoc program that will work in DHBox. The .deb file extension tells us that this is a linux file. The next step is to unpack that file. We do this with this command:

`$ sudo dpkg -i pandoc-1.19.2.1-1-amd64.deb`

Some commands can have nasty side effects, and the operating system won't let you do them unless you specify that you *really* want to do them. That's what the [sudo](https://en.wikipedia.org/wiki/Sudo) achieves. The next part, dpkg with the -i 'flag' is a 'package manager' for installing software. The last part is the file that we used wget to copy to our own machine. To test that pandoc is now installed, type:

`$ pandoc -v`

If all has gone well, DHBox will tell you what version of pandoc you have installed, who it was built by, and a copyright notice.

Now, let's create a file to keep a record of what commands we have been typing. Type:

`$ history`

DHBox returns a list of every command that you've typed. You can 'pipe' that information into a new file like so:

`$ history > dhbox-work-today.md`

When you hit enter, the computer seems to pause for a moment, and then it shows you the command prompt again. How do we know if anything happened? Generally, when working at the command prompt, no news is good news. There are two ways you can check to see if the new file `dhbox-work-today.md` was created. You can click on the 'file manager' (the first folder will have your username; click on that, and then you'll see a list of files) and there it is! Click on the file name, and it will download to your computer where you can open it with a text editor.

The other way is to type:

`$ ls`

at the command line. This 'lists' - ls - all the files in the directory. How do you know what directory you're in? You can use the `pwd` command, which prints the working directory.

Let's take a look inside that new file you created. There is a text editor that you can use, called 'nano'. Type:

`$ nano dhbox-work-today.md`

This opens the text editor, and you can see that the history command has copied its output into the editor. **If you got an error:** Sometimes, tools or commands we want to use are not present in the system. DHBox uses the 'Ubuntu' operating system (the underlying code that makes a PC a PC, a Mac a Mac, etc). We can install all sorts of useful things by using the `apt-get` command. To get and install Nano, try re-installing nano with this command:

`$ sudo apt-get install nano`.

The computer makes things a little more difficult sometimes when you're asking it to do something that changes or adds capabilities, so simply typing `apt-get` wouldn't work. `sudo` tells the computer, I really do want to this (it stands for 'super-user do'). Any 'sudo' command will make the computer ask for your password to confirm that you really do want to run that command.

[Visit this guide to using the Nano text editor](https://www.howtogeek.com/howto/42980/the-beginners-guide-to-nano-the-linux-command-line-text-editor/) which you should check out now.

In Nano, with your file open, make a header (use `#` to indicate a header, remember) at the start of the file which has today's date in it, and add some text explaining what you're trying to do. Then, hit ctrl+x to edit Nano. Nano will ask you if you want to 'Save modified buffer?'. Hit `y`, then when it asks you for the file name, hit enter.

Use the file manager to save a copy of `dhbox-work-today.md` onto your own computer. One last thing: let's convert the markdown file into both Word and HTML. Pandoc is capable of quite sophisticated transformations, but these are two of the easiest. Try this:

`$ pandoc -o todayscommands.docx dhbox-work-today.md`

This says to pandoc, create an output file ( the -o) called 'todayscommands.docx' from 'dhbox-work-today.md'. Type `ls` after running this command to see if you've made the file. Any guesses how to create an HTML file? Pandoc is smart enough to know the kind of output you want from the file extension, so retype the command but use .html instead of .docx this time. Use filemanager to save copies of the .docx and .html files to your own machine. (Incidentally, if you use the arrow up and arrow down keys on your keyboard when you're at the command line, you can page through commands that you've previously typed).

You've done some interesting work - you've installed software into a remote computer, you've copied all of the commands you typed into a new file, you've used markdown and a text editor to add information and context to those commands, and you've used pandoc to transform your basic text into the more complicated formats of Word or HTML.

As you do more work in this workbook, I want you to get in the habit of keeping these copies of what you've done. These are your actual lab notes, and they are invaluable for helping you keep track of what you've been doing and what you've been trying. If you remember the course manual, keeping a lab notebook is part of the assessment of the course.

In the next exercise, we learn to use another piece of software called 'git' which will enable you to set up a remote location for pushing copies of your work to, for safe keeping and for collaboration. For more on why we go to all this trouble, see ['Preserving Your Research Data'](http://programminghistorian.org/lessons/preserving-your-research-data).

[Visit this handy cheat-sheet of keyboard shortcuts and other useful commands for your DHBox command-line work](https://help.ubuntu.com/community/AdvancedCommandlineHowto#Keyboard_shortcuts).

## EXERCISE 3: setting up your github space

It's a familiar situation - you've been working on a paper. It's where you want it to be, and you're certain you're done. You save it as 'final.doc'. Then, you ask your friend to take a look at it. She spots several typos and that you flubbed an entire paragraph. You open it up, make the changes, and save as 'final-w-changes.doc'. Later that day it occurs to you that you don't like those changes, and you go back to the original 'final.doc', make some changes, and just overwrite the previous version. Soon, you have a folder like:

```
|-project
    |-'finalfinal.doc'
    |-'final-w-changes.doc'
    |-'final-w-changes2.doc'
    |-'isthisone-changes.doc'
    |-'this.doc'
```

Things can get messy quite quickly. Imagine that you also have several spreadsheets in there as well, images, snippets of code... we don't want this. What we want is a way of managing the evolution of your files. We do this with a program called [Git](https://git-scm.com/). Git is not a user-friendly piece of software, and it takes some work to get your head around. Git is also very powerful, but fortunately, the basic uses to which most of us put it to are more or less straightforward. There are many other programs that make use of Git for version control; these programs weld a graphical user interface on top of the main Git program. For now, we'll content ourselves with the Github website, which does the same thing more or less, but from a browser.

Firstly, let's define some terms.

+ git is a program that keeps snapshots of the contents of a designated folder; it watches for 'difs' or differences between one snapshot and the next. You 'commit' these snapshots to a repository, which lives on your computer (it's just a folder).
+ _Github_ is a webservice that allows you to share those repositories, and to keep track of those *versions* online, and what's more, to share the repositories and files with multiple collaborators, and _keep everyone's changes straight!_ There are other services that work like Github; Github is just one of the better known services. You can browse Github repositories for code that solves a particular problem for you, software, and data.

NB. Because we are going to use the free version, we cannot make the repositories we create private.

In this exercise, we're going to create a repository via the Github website and use it as a kind of back-up space for the files you created in the previous exercise. In the follow up exercise, you will learn how to do this from the command line.

1. Go to [Github](http://github.com) and sign up for an account. Remember, you don't have to use your real name. If you use a pseudonym, please communicate to me privately what your account is called.
2. Once you're logged in, we will create a new repository called `hist3814o`. Click on the `+` at the top right of the screen, beside your avatar image.
3. Write a short description in the 'description box', and tick off the 'initialize the repository with a readme'. You can also select a license from the drop down box - this will put some standard wording on your repository page about the conditions under which someone else might use (or cite) your code.
4. Click 'create repository'.

At this point, you now have a folder - a repository - on the Github website into which you can deposit your files. It will be at http://github.com/your-account-name/hist3814o. So let's put some materials into that repository.

1. Notice, when you're on your repository's page, that there is a button to 'create new file' and another for 'upload files'. For now, click on 'upload files'.
2. On the page that opens, there is a large grey box in the center of the screen. You can drag and drop files into that box to upload them into your repository. Drag the html file you created in the previous exercise (the one you made with Pandoc, and then saved to your computer via the DHBox filemanager) into the grey box. It will upload the file; you can drag multiple files into the box.
3. Git - and Github - attach messages to any 'commits' you make. These messages are brief notes explaining why you were making the commit. This way, if you ever had to roll back (go back to an earlier version) you can understand the evolution of the repository and find the spot you want. Enter a brief commit message in the commit message box. Then hit the green commit changes button.

Instead of creating multiple versions of a file, you have a single file that has a version history. Neat, eh?

This is perhaps the simplest use case for Github. You can create files directly in the repository as well, by hitting the 'create new file' button, and following the prompts. Github has a brief tutorial on using the website to collaborate with other people on a repository that [you can explore on Github](https://guides.github.com/activities/hello-world/).

**for the remainder of the course, use your hist3814o repository as your scratch pad, your fail log, your open notebook, for showing your work across these modules**

Here is an example 'fail log' as a model - [https://github.com/shawngraham/example-faillog-hist3814](https://github.com/shawngraham/example-faillog-hist3814). 'Fail' is a pretty harsh word: I use it to point out that for everything that works perfectly, there's an awful lot of trial-and-error that happened first *upon which* our successes are built. We need to keep track of this! James Baker calls this, '[de-wizardification](https://cradledincaricature.com/2017/06/29/dewizardification/).'

Some useful vocabulary when discussing git, github, and version control:

+ `repository`: a single folder that holds all of the files and subfolders of your project
+ `commit`: this means, 'take a snapshot of the current state of my repository'
+ `publish`: take a folder on my computer, and copy it and its contents to the web as a repository at github.com/myusername/repositoryname
+ `sync`: update the web repository with the latest commit from the folder on my computer
+ `branch`: make a copy of my repository with a 'working name'
+ `merge`: fold the changes I have made on a branch into another branch (typically, either `master` or `gh-pages`)
+ `fork`: to make a copy of someone else's repo
+ `clone`: to copy a repo online onto your own computer
+ `pull` request: to ask the original maker of a repo to 'pull' your changes into their master, original, repository
+ `push`: to move your changes from your computer to the online repo

### An aside

Many websites - including this workbook - use a Github repository as a way of hosting a website. The video below by historian Jack Dougherty shows how this could be done. Note that the html code that he pastes into an index.html file (the first page of any website is usually called index.html) he got from a different service. You could write a document in markdown, then use pandoc to convert that into an index.html, for example.

<iframe width="560" height="315" src="https://www.youtube.com/embed/ZVejLE8qtOI" frameborder="0" allowfullscreen></iframe>

## EXERCISE 4: a detailed look at using git on the command line

At its heart, Git is a way of taking 'snapshots' of the current state of a folder, and saving those snapshots in sequence. (For an excellent brief presentation on Git, visit [Alice Bartlett's presentation on git](https://speakerdeck.com/alicebartlett/git-for-humans); Bartlett is a senior developer for the Financial Times). In Git's lingo, as stated earlier, a folder on your computer is known as a `repository`. This sequence of snapshots in total lets you see how your project unfolded over time. Each time you wish to take a snapshot, you make a `commit`. A commit is a Git command to take a snapshot of the entire repository. Thus, your folder we discussed above, with its proliferation of documents becomes:

```
|-project
    |-'final.doc'
```    

BUT its commit history could be visualized like a string of pearls, where each pearl is a unique commit. Each one of those pearls represents a point in time when you the writer made a commit; Git compared the state of the file to the earlier state, and saved a snapshot of the `differences`. What is particularly useful about making a commit is that Git requires two more pieces of information about the git: who is making it, and when. The final useful bit about a commit is that you can save a detailed message about *why* the commit is being made. In our hypothetical situation, your first commit message might look like this:

```
Fixed conclusion

Julie pointed out that I had missed
the critical bit in the assignment
regarding stratigraphy. This was
added in the concluding section.
```

This information is stored in the history of the commits. In this way, you can see exactly how the project evolved and why. Each one of these commits has what is called a `hash`. This is a unique fingerprint that you can use to 'time travel' (in Bartlett's felicitous phrasing). If you want to see what your project looked like a few months ago, you `checkout` that commit. This has the effect of 'rewinding' the project. Once you've checked out a commit, don't be alarmed when you look at the folder: your folder (your repository) looks like how it once did all those weeks ago! Any files written after that commit seem as if they've disappeared. Don't worry: they still exist!

What would happen if you wanted to experiment or take your project in a new direction from that point forward? Git lets you do this. What you will do is create a new `branch` of your project from that point. You can think of a branch as like the branch of a tree, or perhaps better, a branch of a river that eventually merges back to the source. (Another way of thinking about branches is that it is a label that sticks with these particular commits.) It is generally considered 'best practice' to leave your `master` branch alone, in the sense that it represents the best version of your project. When you want to experiment or do something new, you create a `branch` and work there. If the work on the branch ultimately proves fruitless, you can discard it. *But*, if you decide that you like how it's going, you can `merge` that branch back into your master. A merge is a commit that folds all of the commits from the branch with the commits from the master.

Git is also a powerful tool for backing up your work. You can work quite happily with Git on your own machine, but when you store those files and the history of commits somewhere remote, you open up the possibility of collaboration *and* a safe place where your materials can be recalled if -perish the thought- something happened to your computer. In Git-speak, the remote location is, well, the `remote`. There are many different places on the web that can function as a remote for Git repositories. You can even set one up on your own server, if you want. To get material *out* of Github and onto your own computer, you `clone` it. If that hypothetical paper you were writing was part of a group project, your partners could clone it from your Github space, and work on it as well!

Let us imagine a scenario.... You and Anna are working together on the project. You have made a new project repository in your Github space, and you have cloned it to your computer. Anna has cloned it to hers. Let's assume that you have a very productive weekend and you make some real headway on the project. You `commit` your changes, and then `push` them from your computer to the Github version of your repository. That repository is now one commit *ahead* of Anna's version. Anna `pulls` those changes from Github to her own version of the repository, which now looks *exactly* like your version. What happens if you make changes to the exact same part of the exact same file? This is called a `conflict`. Git will make a version of the file that contains text clearly marking off the part of the file where the conflict occurs, with the conflicting information marked out as well. The way to `resolve` the conflict is to open the file (typically with a text editor) and to delete the added Git text, making a decision on which information is the correct information.

**Caution** what follows might take a bit of time. It walks you through setting up a git repository in your DHBox; making changes to it; making different branches; and publishing the repository to your space on Github.com.

### git init
4.1. How do you turn a folder into a repository? With the `git init` command. At the command line (remember, the `$` just shows you the prompt; you don't have to type it!):

- make a new directory: `$ mkdir first-repo`
- type `$ ls` (list) to see that the director exists. Then change directory into it: `cd first-repo`. (remember: if you're ever not sure what directory you're in, type `$ pwd`, or print working directory).
- make a new file called `readme.md`. You do this by calling the text editor: `nano readme.md`. Type an explanation of what this exercise is about. Hit ctrl+x to exit, then y to save, leave the file name as it is. **If you get an error to the effect that nano is not found** you just need to install it with `sudo apt-get install nano`. DHBox will ask you for your password again. Once the dust settles, you can make the new file with `nano readme.md`.
- type `$ ls` again to check that the file is there.
- type `$ git init` to tell the Git program that this folder is to be tracked as a repository. If all goes correctly, you should see a variation on this message: `Initialized empty Git repository in /home/demonstration/first-repo/.git/`. But type `$ ls` again. What do you (not) see?

The changes in your repo will now be stored in that *hidden* directory, `.git`. Most of the time, you will never have reason to search that folder out. But know that the config file that describes your repo is in that folder. There might come a time in the future where you want to alter some of the default behaviour of the git program. You do that by opening the config file (which you can read with a text editor). Google 'show hidden files and folders' for your operating system when that time comes.

### git status
4.2. Open your readme.md file again with the nano text editor, from the command line. Add some more information to it, then save and exit the text editor.

- type `$ git status`
- Git will respond with a couple of pieces of information. It will tell you which `branch` you are on. It will list any untracked files present or new changes that are unstaged. We now will `stage` those changes to be added to our commit history by typing `$ git add -A`. (the bit that says `-A` adds any new, modified, or deleted files to your commit when you make it. There are [other options or flags](https://stackoverflow.com/questions/572549/difference-between-git-add-a-and-git-add#572660) where you add *only* the new and modified files, *or* only the modified and deleted files.)
- Let's check our git status again: type `$ git status`
- You should see something like this:

```
On branch master
Initial commit
Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   readme.md```
```
- Let's take a snapshot: type `$ git commit -m "My first commit"`. What happened? Remember, Git keeps track not only of the changes, but *who* is making them. If this is your first time working with Git in the DHBox, Git will ask you for your name and email. Helpfully, the Git error message tells you exactly what to do: type `$ git config --global user.email "you\@example.com"` and then type `$ git config --global user.name "Your Name"`. Now try making your first commit.
- The command above represents a bit of a shortcut for making commit messages by using the `-m` flag to associate the text in the quotation marks with the commit. Open up your readme.md file again, and add some more text to it. Save and exit the text editor. Add the new changes to the snapshot that we will take. Then, type `$ git commit`. Git automatically opens up the text editor so you can type a longer, more substantive commit message. In this message (unlike in markdown) the `#` indicates a line to be ignored. You'll see that there is already some default text in there telling you what to do. Type a message indicating the nature of the changes you have made. Then save and exit the text editor. DO NOT change the filename!

Congratulations, you are now able to track your changes, and keep your materials under version control!

### git merge

4.3. Go ahead and make some more changes to your repository. Add some new files. Commit your changes after each new file is created. Now we're going to view the history of your commits. Type `$ git log`. What do you notice about this list of changes? Look at the time stamps. You'll see that the entries are listed in reverse chronological order. Each entry has its own 'hash' or unique ID, the person who made the commit and time are listed, as well as the commit message eg:

```
commit 253506bc23070753c123accbe7c495af0e8b5a43
Author: Shawn Graham <shawn.graham@carleton.ca>
Date:   Tue Feb 14 18:42:31 2017 +0000

Fixed the headings that were broken in the about section of readme.md

```

- We're going to go back in time and create a new branch. You can escape the `git log` by typing `q`. Here's how the command will look: `$ git checkout -b branchname <commit>` where `branch` is the name you want the branch to be called, and `<commit>` is that unique ID. Make a new branch from your second last commit (don't use < or >).
- We typed `git checkout -b experiment 253506bc23070753c123accbe7c495af0e8b5a43`. The response: `Switched to a new branch 'experiment'` Check git status and then list the contents of your repository. What do you see? You should notice that some of the files you had created before seem to have disappeared - congratulations, you've time travelled! Those files are not missing; but they *are* on a different branch (the master branch) and you can't harm them now. Add a number of new files, making commits after each one. Check your git status, and check your git log as you go to make sure you're getting everything. Make sure there are no unstaged changes - everything's been committed.

4.4. Now let's assume that your `experiment` branch was successful - everything you did there you were happy with and you want to integrate all of those changes back into your `master` branch. We're going to merge things. To merge, we have to go back to the master branch: `$ git checkout master`. (Good practice is to keep separate branches for all major experiments or directions you go. In case you lose track of the names of the branches you've created, this command: `git branch -va` will list them for you.)

- Now, we merge with `$ git merge experiment`. Remember, a merge is a special kind of commit that rolls all previous commits from both branches into one - Git will open your text editor and prompt you to add a message (it will have a default message already there if you want it). Save and exit and ta da! Your changes have been merged together.

### git push
4.5. One of the most powerful aspects of using Git is the possibility of using it to manage collaborations. To do this, we have to make a copy of your repository available to others as a `remote`. There are a variety of places on the web where this can be done; one of the most popular at the moment is [Github](http://github.com). Github allows a user to have an unlimited number of `public` repositories. Public repositories can be viewed and copied by anyone. `Private` repositories require a paid account, and access is controlled. If you are working on sensitive materials that can only be shared amongst the collaborators on a project, you should invest in an upgraded account (note that you can also control which files get included in commit; [visit Github for help on ignoring files](https://help.github.com/articles/ignoring-files/). In essence, you simply list the file names you do not want committed; [visit Github for an example on listing ignored files](https://gist.github.com/octocat/9257657)). Let's assume that your materials are not sensitive.

- login to Github
- On the upper right part of the screen there is a large + sign. Click on that, and select `new public repository`
- On the following screen, give your repo a name.
- DO NOT 'initialize this repo with a readme.md'. Leave `add .gitignore` and `add license` set to NONE.
- Click the green 'Create Repository' button.
- You now have a space into which you will publish the repository on your machine. At the command line, we now need to tell Git the location of this space. We do that with the following command, where you will change `your-username` and `your-new-repo` appropriately:
```
$ git remote add origin https://github.com/YOUR-USERNAME/YOUR-NEW-REPO.git
```
g. Now we push your local copy of the repository onto the web, to the Github version of your repo:
```
git push -u origin master
```

*NB* If you wanted to push a `branch` to your repository on the web instead, do you see how you would do that? If your branch was called `experiment`, the command would look like this:

```
$ git push origin experiment

```

- The changes can sometimes take a few minutes to show up on the website. Now, the next time you make changes to this repository, you can push them to your Github account - which is the 'origin' in the command above.  Add a new text file. Commit the changes. Push the changes to your account.

### git clone
4.6. Imagine you are collaborating with one of your classmates. Your classmate is in charge of the project, and is keeping track of the 'official' folder of materials (eg, the repo). You wish to make some changes to the files in that repository. You can manage that collaboration via Github by making a copy, what Github calls a `fork`.
- Make sure you're logged into your Github account on the Github website. We're going to fork an example repository right now by going to [https://github.com/octocat/Spoon-Knife](https://github.com/octocat/Spoon-Knife). Click the 'fork' button at top-right. Github now makes a copy of the repository in your own Github account!
- To make a copy of that repository on your own machine, you will now clone it with the `git clone` command. (Remember: a 'fork' copies someone's Github repo into a repo in your OWN Github account; a 'clone' makes a copy on your own MACHINE). Type:
```
$ cd..
$ pwd
```
We do that to make sure you're not _inside_ any other repo you've made! Make sure you're not inside the repository we used in exercises 1 to 5, then proceed:

```
$ git clone https://github.com/YOUR-USERNAME/Spoon-Knife
$ ls
```
You now have a folder called 'Spoon-Knife' on your machine! Any changes you make inside that folder can be tracked with commits. You can also `git push -u origin master` when you're inside it, and the changes will show up on your OWN copy (your fork) on Github.com.
c. Make a fork of, and then clone, one of your classmates' repositories. Create a new branch. Add a new file to the repository on your machine, and then push it to your fork on Github. Remember, your new file will appear on the new branch you created, NOT the master branch.

### pull request
4.7. Now, you let your collaborator know that you've made a change that you want her to `merge` into the original repository. You do this by issuing a `pull request`. But first, we have to tell Git to keep an eye on that original repository, which we will call `upstream`. You do this by adding that repository's location like so:

- type (but change the address appropriately):

```
$ git remote add upstream THE-FULL-URL-TO-THEIR-REPO-ENDING-WITH-.git
```

- You can keep your version of the remote up-to-date by fetching any new changes your classmate has done:
```
$ git fetch upstream
```

- Now let's make a `pull` request (you might want to [bookmark Github's help document for pull requests](https://help.github.com/articles/creating-a-pull-request/)). Go to your copy of your classmate's repository at your Github account. Make sure you've selected the correct branch you pushed your changes to, by selecting it from the Branches menu drop down list.
- Click the 'new pull request' button.
- The new page that appears can be confusing, but it is trying to double check with you which changes you want to make, and where. *'Base Branch'* is the branch where you want your changes to go, ie, your classmate's repository. *'head branch'* is the branch where you made *your* changes. Make sure these are set properly. Remember: the first one is the TO, the second one is the FROM: the place where you want your changes to go TO, FROM the place where you made the changes.
- A pull request has to have a message attached to it, so that your classmate knows what kind of change you're proposing. Fill in the message fields appropriately, then hit the 'create pull request' button.

### git merge again
4.8. Finally, the last bit of work to be done is to accept the pull request and `merge` the changes into the original repository.
- Go to your repository on your Github account. Check to see if there are any 'pull requests' - these will be listed under the 'pull requests' tab. Click on that tab.
- You can merge from the command line, but for now, you can simply click on the green 'merge pull request' button, and then the 'confirm merge' button. The changes your classmate has made have now been folded into your repository.
- To get the updates on your local machine, go back to the command line and type
```
$ git pull origin master
```

Phew. You might want to do `$ history > recentcommands.md` just to remember what you've done. And then commit that to a repository.

-----

## Conclusion

In the modules to come, we will be using DHBox as we find data, fetch data, wrangle data, analyze data, and visualize data. It becomes very important that you note the kinds of commands you use or try, the thinking that you were doing at that point, and so on. You want to leave yourself (and anybody who comes after) breadcrumbs so that you understand what you were doing. Quick notes written in markdown, piping the history of what you've done to a file, and keeping those files in a repository alongside any other code or files that you may make will set you on the path to open access research and computational reproducibility. As Martha might say, 'and that's a good thing'.
