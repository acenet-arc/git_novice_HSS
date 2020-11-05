---
title: "GitHub Pages"
teaching: 10
exercises: 5
questions:
- "How can I host a website?"
objectives:
- "Learn how to host a static website with documentation or a blog on a Git Platform."
keypoints:
- "GitHub offers a way hosting a website on their platform."
- "The pages are stored in a Git repository."
- "The pages are static in a sense that there are no server-side scripts or databases."
- "GitHub builds pages from Markdown files with 'Jekyll'"
- "Jekyll is executed whenever commits are pushed to the server."
---

GitHub, offers hosting pages directly from a Git repository.

<!--Sometimes hosting a few simple Wiki pages is not sufficient for a project
and you want to host a small website using your own design or an amount of 
content that exceeds the capabilities of Wiki pages.

When you create a repository with the name `<username>.github.io`, the content 
of that repository will be available under "https://<username>.github.io".
Other repositories can be set serve pages under "https://<username>.github.io/<reponame>".

The same methodology applies to GitLab and Bitbucket with the `<username>.gitlab.io`
and `<username>.bitbucket.io` domains respectively.  GitHub and GitLab also 
allow configuring a custom domain, e.g. `www.example.com`.
-->

### Creating a web page with GitHub pages

Let's try out serving a small page on GitHub from within our `planets` repository.

First we need to activate the "Pages" functionality for this repository on GitHub:

1. go to the repository's settings, 
2. scroll down to "GitHub Pages"
3. in the dropdown select **master branch / docs folder**
4. click **Save**
5. we **don't** use the Theme Chooser at this point.

Continuing in our planets repository directory open a new file `_config.yml` in the nano editor

~~~
$ nano _config.yml
~~~
{: .bash}

and add the following content:

```yaml
# _config.yml
# Jekyll configuration
name:  My Cool Page
title: My Cool Page
description: A Documentation Page created with Jekyll
theme: jekyll-theme-architect
```
Exit and save that file. 

Next create a new file `index.md`
~~~
$ nano index.md
~~~
{: .bash}

and add the following [Markdown](https://daringfireball.net/projects/markdown/syntax) content:

```markdown
<!-- index.md -->
# My Testing Docs Page

It Works! :-)

1. Have a `_config.yml` file setting a `title`, `name`, `description` and `theme`.
2. Add an `index.md` file with the landing page in Markdown.
3. Add more `*.md` files, e.g. `about.md`
```

Now we commit the changes and push them to GitHub:

~~~
$  git add _config.yml index.md
$  git commit -m "my first GitHub page"
$  git push origin master
~~~
{: .language-bash }

Switch back to the browser and reload the settings page.  Under the GitHub
pages section you should now see the URL under which the site was published
(`https://<username>.github.io/planets/`).  Click on that link -- et viol&agrave;!

From the data inside the [Jekyll][jekyll] configuration file `_config.yml` 
and landing page `index.md` in Markdown format, a website was build on
the GitHub servers and is now available to be viewed by anyone.


> ## Change the Jekyll theme
> 
> Go back to the repository's settings and use the *Theme Chooser* to select
> a different theme.  
> Notice that this has generated a new commit.  Use `git pull origin` to pull
> this change into your local repository.
>
{: .challenge }



{% include links.md %}