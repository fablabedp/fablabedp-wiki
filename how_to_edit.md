# How to Edit this Wiki

**[Wiki Home](https://hackmd.io/@fablabedp/home)**

This wiki is also available on [GitHub](https://raw.githubusercontent.com/fablabedp/fablabedp-wiki).

To maintain synchronisation between HackMD and GitHub, it is necessary to pull and push changes between them (see [Editing an Existing Page](#editing-an-existing-page)).


## Writing in Markdown

There are many good guides to writing in markdown, but here is a nice succinct one [github/cuonggt/markdown_guide.md](https://gist.github.com/cuonggt/9b7d08a597b167299f0d)

Here is a more complete overview from the original creator of markdown: https://daringfireball.net/projects/markdown/

There is a comprehensive guide to markdown and HackMD here: https://hackmd.io/c/tutorials/


## Making a New Page

1. Create a new markdown file for the page in the appropriate folder, and add some content.  To facilitate navigation, add a link to the wiki home at the top of the page, after the page title:  

	` **[Wiki Home](https://hackmd.io/@fablabedp/home)**`  

2. Make a commit for the new page to the repository on GitHub.
3. On the HackMD dashboard, select `New Note`
4. In the empty Note page, select `Pull from Github`, then select the `fablabedp-wiki` repo, `main` branch, and then navigate to the page and select `Pull`

	![](https://raw.githubusercontent.com/fablabedp/fablabedp-wiki/main/resources/images/pull_from_github.png)  

5. In the pull dialog, select `Apply all changes`
6. Edit the page title and add any necessary tags.  The first tag selected will be used as a category organiser on the HackMD dashboard.  

	![](https://raw.githubusercontent.com/fablabedp/fablabedp-wiki/main/resources/images/title_and_tags.png)  

	![](https://raw.githubusercontent.com/fablabedp/fablabedp-wiki/main/resources/images/title_and_tags_edited.png)  

7. When the page is ready to publish, Select `Share` and set note permisssions to read: `Everyone` and write: `Only me`.  If necessary you can customise the page URL, then agree to the HackMD community guidelines and select `Publish`.

	![](https://raw.githubusercontent.com/fablabedp/fablabedp-wiki/main/resources/images/publish.png)  

8. Edit the wiki home page to add a link to the new page.  In order to make the links functional on GitHub, use HackMD absolute urls (eg: https://hackmd.io/50M-O-CoRtC3L6Bp-058dw)


## Editing an Existing Page

### Syncing from GitHub to HackMD

After pushing a commit to GitHub, any pages edited need to be manually updated on HackMD.  In the page options select `Versions and GitHub Sync`.

![](https://raw.githubusercontent.com/fablabedp/fablabedp-wiki/main/resources/images/github_sync.png)  

If there are any new changes to synchronise there will be an orange dot on the Pull icon.  

![](https://raw.githubusercontent.com/fablabedp/fablabedp-wiki/main/resources/images/pull_push.png)  

Select `Apply All Changes`, and then you can close the _Versions and GitHub Sync_ window.


### Syncing from HackMD to GitHub

After editing a page on HackMD, these can be pushed as a commit to GitHub.  In the page options select `Versions and GitHub Sync`, the select `Push`, and with the main branch select click `Push`.  If needed you can customise the commit name and description, but this is optional.


## Adding Images

Images can be added to the github repository for embedding in pages.  In this case use the following link format as the image source:  

`![](https://github.com/fablabedp/fablabedp-wiki/raw/main/images/logo_FabLabEDP.jpg)`  