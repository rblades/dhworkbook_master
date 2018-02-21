# Creating a GitHub pages site with MkDocs

In [Module 5](../module-5/Exercises/#exercise-2-typography), you learned how to set up and serve a basic webpage on GitHub's gh-pages. GitHub allows you to host a website on a personal URL with the syntax `https://myname.github.io`. Many developers will use a static site generator to create a simple website run on gh-pages. Some popular static site generators are [Jekyll](https://jekyllrb.com/), [Hugo](https://gohugo.io/), and [MkDocs](http://www.mkdocs.org/). In fact, this website is built with MkDocs.

Static site generators are command line tools that use templates to build and create websites. Users define basic information in a yaml or toml filetype, write in markdown, and use a simple command to build it into a functioning static site. Due to the popularity of static site generators, most contain simple methods to link it to gh-pages. 

In this exercise, we will use MkDocs in the DH Box to build a site that updates to GitHub and pushes changes to a `https://myname.github.io` URL. In this exercise we will use DH Box to download MkDocs and build the site. Although your changes will be saved in a GitHub repository, when your DH Box account expires, you will have to clone the website again and redowload everything. Therefore, if you want to use your MkDocs site past the purposes of this course, you may want to follow these steps on your desktop. These steps will be similar to using Mac's terminal, but may be different on a Windows machine.

## Preparing MkDocs in DH Box

1. Navigate to the DH Box command line.

2. Type `$ sudo pip install mkdocs` into the command line.

3. Type `$ mkdocs --version` to ensure MkDocs was installed properly.

4. Type `$ mkdocs new my-site` or whatever you want your site to be called. Mine is called `static-site`.

5. Typically, you could now view your site by typing `$ mkdocs serve`. This would not work within DH Box, though, since DH Box already runs within your browser. It will work from your desktop terminal.

6. Type `$ ls` to view the files MkDocs created. You will define your site within the `mkdocs.yml` file.

7. Type `$ nano mkdocs.yml` to open the config file.

8. Change the `site_name` to your site's name.

9. Paste the following underneath `site_name`:

        pages:
            - Home: index.md
        theme: readthedocs

    This sets up our Home and About pages and adds the theme called Read the Docs.

10. Hit ctrl-x, Y, enter to save and exit nano.

## Creating a git repository

1. Navigate to GitHub and create a new repository with the same name as your MkDocs folder. For example, my MkDocs folder is called `static-site`. Therefore, I call my GitHub repository `static-site`.

2. Navigate back to the command line.

3. Type `$ git init` to initialize the MkDocs folder as a git repository.

4. Type `$ git add .` to add the files and folders.

5. Type `$ git commit -m "First commit"` to commit your changes.

6. Type `$ git remote add origin https://github.com/<yourusername>/<yourrepository>.git`, making sure to add your URL to the GitHub repository.

7. Type `$ git push -u origin master` to push your changes.

8. Type `$ mkdocs gh-deploy` to push your folder to a gh-pages site.

    MkDocs will show a message saying `INFO    -  Your documentation should shortly be available at: https://myname.github.io/my-site/`. This means it pushed your changes to a project folder and not the main `https://myname.github.io/`. 

9. Navigate to your URL `https://myname.github.io/my-site/`. You should now see a webpage that looks a lot like the course website.

## Adding content to your site

Let's say we now want to add an About page and a Blog page to our site. We need to define and create these files.

1. Navigate to the command line.

2. Type `$ ls` to view your MkDocs files and folders. You will notice now a `site` folder has been generated. This is simply the site folder created by MkDocs which is served on your `github.io` site.

3. Type `$ nano mkdocs.yml` to open the config file.

4. Add an about page and a posts page. Your file should contain the following:

        site_name: Static Site Example
        pages:
            - Home: index.md
            - About: about.md
            - Blog: blog.md
        theme: readthedocs

5. Hit ctrl-x, Y, enter to save and exit nano.

6. Type `$ cd docs` to enter the docs folder.

7. Type `$ touch about.md` to create the About file and `touch blog.md` to create the blog file.

8. Type `$ ls` to make sure the files were created.

9. Type `$ cd ..` to go back to the main MkDocs folder.

10. Type `$ git add .` to add the files.

11. Type `$ git commit -m "Added about and blog files"` to commit your changes.

12. Type `$ git push -u origin master` to push your changes.

    This ensures all your changes are pushed to your GitHub repository.

13. Type `$ mkdocs gh-deploy` to push your folder to a gh-pages site.

14. Reload your gh-pages site `https://myname.github.io/`.

    It may take some time for your changes to update to your gh-pages site.

15. Back in your `docs` folder, you can use nano to edit any of the markdown files. If you add any files, make sure to declare them in `mkdocs.yml`. 

## Customizing your theme

MkDocs also allows you to customize your theme. We don't want to directly edit the theme files, so we will create a new one.

1. Navigate to the command line.

2. In your main MkDocs folder, type `$ nano mkdocs.yml` to open your configuration file.

3. Add the following text below the other configuration details:

        extra_css:
          - 'css/extra.css'

    This declaration tells the site to first look for styles in a folder called `css` in a file called `extra.css` before going to the default theme.

4. Hit ctrl-x, Y, enter to save and exit nano.

5. Type `$ cd docs` to navigate to the docs folder.

6. Type `$ mkdir css` to create a folder called css.

7. Type `$ cd css` to enter the css folder.

8. Type `$ nano extra.css` to create an enter a css file called extra.

    Let's change the font of our site to Open Sans.

9. Add the following your css file:

        h1, h2, h3, h4, h5, h6, legend {
            font-family: 'Open Sans', sans-serif;
        }

10. Hit ctrl-x, Y, enter to save and exit nano.

11. Type `$ cd ..` twice to go back up to your main MkDocs folder.

12. Use git to add your files, commit, push, and then use mkdocs to deploy to gh-pages to view your changes.

    You can now use you knowledge to customize your theme. Remember to use your browser inspector tool to check which rules you want to change.
