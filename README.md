# Axiom data portal help documentation

This GitHub repository is where the help documentation lives for data portals developed by [Axiom Data Science](https://www.axiomdatascience.com) (Axiom). Contributions to this documentation by our partner organizations are welcome via pull requests. These instructions describe how the repository is structured and how partners can contribute custom content for their data portal.

## Common terms

*Data portal*: a web-based application for exploring, visualizing, and interacting with environmental data. A data portal is composed of a **Data Catalog** (a search page with a list of available datasets) and a **Data Map** (a map-based page with data displayed spatially).

*Brand*: a partner organization with their own version of the data portal. The basic data portal technology is shared among Axiom's partners, but each data portal has unique features and "branding" (e.g., logos, theme colors) specific to its partner organization.

*Repository (repo)*: a collection of files saved together on GitHub.

*Fork*: to make a copy of (specifically, to make a copy of a GitHub repo that you can work on without affecting the master copy).

*Pull request*: a way to let a project owner (in this case, Kyle Wilcox (@kwilcox)) know that you've made edits you would like to be added to the master copy.

*Edits*: any kind of change to the content of a file in the repo. Edits can include adding, changing, or deleting text, images, or code. Basically anything that changes any single character of any file in the repo is considered an edit by GitHub.

## Introduction

The data portal help documentation is set up as a website, which you can think of as a bunch of HTML files. Those HTML files are generated by [Sphinx](www.sphinx-doc.org), which is a Python-based tool that turns plain-text files into HTML files.

In order for Sphinx to work its magic, those plain-text files have to be formatted according to certain conventions. In this case the convention is something called [reStructuredText](http://www.sphinx-doc.org/en/stable/rest.html) (RST). Files formatted according to the RST conventions have the extention ".rst" (`index.rst`, for example).

As Sphinx is turning those RST files into HTML, it applies cascading style sheets (CSS) to make them look nice. For the data portal help docs, we've chosen the familiar [Read the Docs](https://docs.readthedocs.io/en/latest/) theme for our CSS. Sphinx also adds nice touches like a search bar, a navigation pane, and your brand's logo.

## How this repository is organized

The data portal help docs repository is organized into 3 directories, which you can think of as folders:

1. The main folder, where 2 types of files live:
	1. RST files, where our primary content lives:
		* ``index.rst``, which is the home page of the docs site
		* ``overview.rst``, which is the main overview page with most of the narrative content describing the data portal's features
	1. Admin type files, such as ``conf.py`` and ``make.bat``, which we can safely ignore
1. The ``partner_content`` subfolder, where a subdirectory for each brand's special content lives (in addition to a ``global`` folder). Each partner's folder contains the following:
	1. An ``images`` folder for custom screenshots and GIFs
	1. A ``static`` folder for custom CSS
	1. A ``config.yml`` file for brand-specific details (e.g., data portal title, partner logo file name)
	1. A ``substitutions.txt`` file for defining short-cut names for brand-specific images
1. The ``custom`` subfolder, where a global CSS file lives that we don't have to worry about
1. The ``how-to`` subfolder, which has ``catalog`` and ``map`` subdirectories where individual files for the how-to pages live

## How to add content for your data portal

If your organization has a data portal with its own branding (e.g., logo, data portal name), you can add custom content for your data portal's help docs. To do this, you must first **fork** (make a copy of) the master [portal docs repo](https://github.com/axiom-data-science/portal-docs).

You can find the official GitHub help docs on forking a repo [here](https://help.github.com/articles/fork-a-repo/).

**Please note that you only need to fork the master portal docs repo once.** Once you've forked the repo you effectively have your own working copy. You can continue editing your copy in the future without having to "re-fork" each time.

Once you've made your edits, you can request that those edits be added to the master portal docs repo by making a **pull request**.

You can find the official GitHub help docs on pull requests [here](https://help.github.com/articles/about-pull-requests/).

## How to format screenshots and GIFs

The data portal help docs will continue to look clean and professional if all images (screenshots and GIFs) are created using the same basic guidelines.

**For screenshots:**

* Take screenshots with your browser window at 100% magnification
* Adjust your browser window to get the best view of what you're trying to illustrate
* Crop out your browser window title bar so you can't see the address or any extra tabs you have open
* In your ``substitutions.txt`` file, define your screenshot to have width = ``1600px`` and height = ``800px``

**For GIFs:**

* Make GIFs with your browser window at 100% magnification
* Adjust your browser window to get the best view of what you're trying to illustrate
* Make GIFs with a height of ``1200px`` and a width of ``600px``
* Use 10 frames per second caputre rate
* Compress GIFs before adding them (e.g., use the "slight" setting on a GIF optimizer like [this one](http://gifgifs.com/optimizer/).

### How to add a new page for your portal only

1. Go to the ``partner_content`` folder
1. Go to your brand's subfolder
1. Go to your ``pages`` subfolder
1. Create a new RST file (e.g., ``my_new_page.rst``)
1. Add your content to that file using the [RST](http://www.sphinx-doc.org/en/stable/rest.html) conventions
1. Save your file
1. Make a pull request

### How to add a new how-to page for all portals

1. Check with Kyle Wilcox (kyle@axiomdatascience.com)

### How to edit an existing page

1. Go to the ``partner_content`` folder
1. Go to your brand's subfolder
1. Go to your ``pages`` subfolder
1. Open the RST file (e.g., ``my_existing_page.rst``) you would like to edit
1. Add your content to that file using the [RST](http://www.sphinx-doc.org/en/stable/rest.html) conventions
1. Save your file
1. Make a pull request

### How to add a new screenshot or GIF

**Make the image**

1. Create the screenshot or GIF using the guidelines above
1. Go to the ``partner_content`` folder
1. Go to your brand's subfolder
1. Go to your ``images`` subfolder
1. Save the file there (e.g., ``my_new_screenshot.png``)

**Add it to your substitutions file**

1. Back out of your ``images`` folder to get to your subfolder in ``partner_content``
1. Open the ``substitutions.txt`` file
1. Add a line to the appropriate section to create an alias for your image file (more about substitutions can be found [here](http://www.sphinx-doc.org/en/stable/rest.html#substitutions))

**Finally**

1. Make a pull request

### How to replace an existing image

1. Create your new screenshot or GIF using the guidelines above
1. Go to the ``partner_content`` folder
1. Go to your brand's subfolder
1. Go to your ``images`` subfolder
1. Delete the old file
1. Save the file new file in its place and **be sure it has the exact same name as the old file**

## Conclusion

If you have a question that isn't answered here, or if you find this guidance confusing or otherwise unhelpful, please contact Kyle Wilcox (https://github.com/kwilcox) directly. Your feedback will help us improve this documentation for future users.

