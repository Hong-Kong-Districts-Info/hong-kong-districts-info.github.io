# site
Hugo site files for Hong Kong Districts Info

# Contribution Guide

To contribute to this site, you will first need to install **Hugo** and **git**. You will also need to set up a sub-module so that the local directory containing the Hugo site files would point to two places:

1. `site` - the full directory containing the actual site files. 
2. `hong-kong-districts-info.github.io` - the sub-directory called `public`, which points to https://github.com/Hong-Kong-Districts-Info/hong-kong-districts-info.github.io. This sub-directory contains the static HTML files generated by Hugo. 

## The set up

The **Hong Kong Districts Info** website is hosted on GitHub, via [GitHub Pages](https://pages.github.com/). The website itself is a _static site_ set-up, meaning that all the HTML files are pre-generated and are delivered to the user's web browser exactly as stored, in contrast to dynamic web pages which are generated by a web application. [Hugo](https://gohugo.io/) is the static site generator used for building this website, which is itself open-source and is a library written in [Go](https://golang.org/), an open-source language by Google. There are several reasons why we chose to use **Hugo**:

- Speed - it claims to be the world’s fastest framework for building websites, and certainly in our experience it is very fast
- Ease of use - the language itself is very simple and can be picked up easily by someone with minimal programming knowledge
- Popularity - the popularity makes it easy to find resources when troubleshooting an issue

The entire website set-up is open-source, fast to load (for the user), and fast to deploy (for the developer). At the time of writing there is no plan to move the site to a custom domain name.

## Installing Hugo

Follow the instructions on the [Hugo documentation page](https://gohugo.io/getting-started/installing/#windows) to install Hugo.

## Setting up git

If git is not installed already, follow the instructions on [this page](https://git-scm.com/book/en/v2/Getting-Started-Installing-Git) to install git.

The following instructions for the set up is for Windows.

1. Start with navigating to your local directory using Command Prompt (type `cmd` in your Windows bar). Say you want to set up the website files in `MyFolder/WebFiles/`. The following code _changes your directory_ with the specified file path (substitute accordingly):
``` 
cd Documents/MyFolder/WebFiles
```

1. Next, run `git clone https://github.com/Hong-Kong-Districts-Info/site.git`. This will create a clone of the `site` repository from GitHub under `MyFolder/WebFiles/`. You should be able to see the `site` files using Windows Explorer.

1. Run `cd site` to change your current path to within the site files. 

1. Run `hugo server` and and open your browser to http://localhost:1313. This is your _local deployment_ of the website.

1. Once you are happy with the results:
  - Press Ctrl+C to kill the server
  - Before proceeding run `rm -rf public` to completely remove the public directory

1. `git submodule add -b master https://github.com/Hong-Kong-Districts-Info/hong-kong-districts-info.github.io.git public`. This creates a git submodule. Now when you run the `hugo` command to build your site to public, the created public directory will have a different remote origin (i.e. hosted GitHub repository).

Please see https://gohugo.io/hosting-and-deployment/hosting-on-github/ for the original instructions.

## Making a change and testing locally

You can run `hugo server` and and open your browser to http://localhost:1313 to test the website locally.

You can test this by duplicating and editing a Markdown file in `site/content/portfolio/`, and the site should update accordingly.

## Deploying the site

_To be written..._
