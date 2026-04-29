# Setup Guide

A step-by-step guide to setting up a new website with the Pressmark theme, adding it to an existing site, and deploying it to the web.

## On this page

- [Starting a new site with Pressmark](#starting-a-new-site-with-pressmark)
  - [Using the GitHub Template](#using-the-github-template)
  - [Downloading the full code](#downloading-the-full-code)
  - [Basic Quarto website commands](#basic-quarto-website-commands)
- [Adding Pressmark to an existing website](#adding-pressmark-to-an-existing-website)
- [Deploying your site to the web](#deploying-your-site-to-the-web)
  - [GitHub Pages](#github-pages)
  - [Uploading the HTML](#uploading-the-html)

![](./static/setup.jpeg)

Composition Mechanical Movement cart (1919) - Ferdinand Leger

## Starting a new site with Pressmark

So, you want your own website, Great! You don’t need to be a web developer to do that, and you don’t need to know how to code. With Quarto (and Pressmark), it’s quite easy to get a simple website up and running.

### Using the GitHub Template

If you already have a GitHub account, this is probably the easiest way. Just go to the [Pressmark GitHub Repo](https://github.com/skriptum/quarto-pressmark) and click the “Use this template” button. This will create a new repository in your GitHub account with the Pressmark theme already set up. You can then clone this repository to your local machine, make changes, and push them back to GitHub.

### Downloading the full code

If you don’t have a GitHub account, or if you prefer to work locally, you can download the full code as a ZIP file. Go to the [Pressmark GitHub Repo](https://github.com/skriptum/quarto-pressmark) and click the green “Code” button, then select “Download ZIP”.

Extract the contents to a folder of your choice, and you’re ready to go. Make sure you have [Quarto](https://quarto.org/) installed, and navigate to the folder in your terminal.

### Basic Quarto website commands

To render your website, run the following command:

``` bash
quarto render
```

This will generate the HTML files for your website in the `_site` folder. To preview your website locally, run:

``` bash
quarto preview
```

It will open your website in your default browser. Now, you can adjust the content in the editor of your choice, and see it change in real time.

------------------------------------------------------------------------

## Adding Pressmark to an existing website

If you already have a Quarto website and want to switch to the Pressmark theme, you can do so by following these steps:

1.  Download the `pressmark.scss` from the [GitHub Repo](https://github.com/skriptum/quarto-pressmark/blob/main/pressmark.scss) and add it to your website’s folder.
2.  Now, adjust your website’s `_quarto.yml` file to include the Pressmark theme. Add the following lines

``` yaml
format:
  html:
    theme: pressmark.scss
```

3.  Use the Pressmark features (e.g the Drop Caps from [Typography](./features/typography.qmd)), or adjust the colors

Render your website and you should be good to go!

Alternatively, if you already have a custom scss file, you can also import `pressmark.scss` into your existing scss file, and adjust the theme settings there.

``` css
@import "pressmark.scss";
```

You’ll probably need to adjust some of your styles / layout to make it work with the Pressmark theme, but if you alread have a custom scss file, you probably know your way around CSS, so that shouldn’t be a problem.

> Irrespective of how you set up your website, it would be cool if you can attribute the theme by adding a link to the [Docs](https://mdwm.org/quarto-pressmark/), so that other people can find it and use it for their own projects. You can do this in the footer, or in the sidebar, or anywhere else you like.

------------------------------------------------------------------------

## Deploying your site to the web

There are hundreds of ways to deploy some HTML files to the web, I found GitHub Pages to be the easiest and most straightforward way.

### GitHub Pages

If you used the GitHub Template, you can simply go to the “Settings” of your repository, scroll down to the “GitHub Pages” section, and select the branch you want to deploy from. As the template already includes a gh-pages workflow, you just need to push your changes to the main branch, and GitHub will take care of the rest.

For it to work, you need to select the `gh-pages` branch as the source for GitHub Pages. You don’t need to upload the `_site` folder to GitHub, so make sure it’s included in your `.gitignore` file.

Your new website should be live within a few minutes at `https://yourusername.github.io/yourrepositoryname/`.

### Uploading the HTML

If you don’t want to use GitHub Pages, you can also upload the generated HTML files in the `_site` folder to any web hosting service that supports static sites. Some popular options include Netlify, Vercel, and AWS S3.

This may seem easier at first, but if you want to update your website, you’ll need to re-upload the HTML files every time, which can be a bit of a hassle. So I recommend using GitHub Pages if you can, as it allows for easy updates and version control.

------------------------------------------------------------------------

All of the above was just a very short introduction to get you started. For more detailed instructions, troubleshooting tips, and advanced features, check out the [Quarto Documentation](https://quarto.org/).
