# ccmcr19-workshop-build-your-lesson
Workshop "How to make a Carpentries-style lesson" at CarpentryConnect 2019 in Manchester

## Requirements

- GitHub account
- Git
- Python
- Jekyll (may be omitted for the very beginning)

## Setup

See [details here](http://carpentries.github.io/lesson-example/setup.html).

### Import the repository with the lesson template

This is done using [GitHub's importer](https://github.com/new/import).

The URL of the repository to import is <https://github.com/carpentries/styles>.

We will assume that your username is `user` and the name of the
new lesson is `your-lesson`. You will need to replace them by 
their actual values.

## Clone the repository and specify the location of the template

    git clone -b gh-pages https://github.com/user/your-lesson.git
    cd your-lesson
    git remote add template https://github.com/carpentries/styles.git
    git config --local remote.template.tagOpt --no-tags
    git checkout gh-pages
    
## Autogenerate further files

    ./bin/lesson_initialize.py

## Check the result
    
You can now call `git status` to check which files have been created.

If you have installed Jekyll, call

    make serve
    
and follow instructions to be able to view the lesson website locally.

## Edit `_config.yml`

Specify some parameters, as instructed in this file. If you have
Jekyll, check the website locally to check that the changes have
been applied. You can check that all links on the main page are
also working.

## Commit and push

Using Git, commit all newly generated files and push commit to
GitHub.

This is also a suitable moment to look at the content of 
those files to get an idea about their purpose and find out 
how they are rendered on the lesson website. Additional 
information about the file structure could be found 
[here](http://carpentries.github.io/lesson-example/03-organization/index.html).

## Check the online version of the lesson website

- Check the "settings" menu of the lesson repository
- Check that the lesson website is available
- Specify the description and the URL of the website on the repository page
- Specify repository topics

## Make changes using GitHub web-interface

Use "Improve this page link" to do this.

## Synchronise local copy

    git pull

## Check the lesson

    make lesson-check
    
## Analyse report and fix problems

Fix URL of the lesson issue tracker

## What next:

- Main debugging technique: if changes do not appear, use `make serve` and analyse error messages

- Look for more `FIXME` items: `grep -R --include=*.md FIXME *`

- Look at [Markdown formatting](http://carpentries.github.io/lesson-example/04-formatting/index.html).

- Eventually may need to update style using the remote `template`.
