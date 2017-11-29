# Public Money Public Code – publiccode.asia

This is the website of "Public Money, Public Code" [publiccode.asia](https://publiccode.asia). It is based on [Hugo](https://gohugo.io).


## Table of Contents

- [Contribute](#contribute)
- [Translate](#translate)
- [Build](#build)
- [HowTos and FAQs](#howtos-and-faqs)
- [Maintainers](#maintainers)
- [Licence](#licence)


## Contribute

### Prerequisites

In order to modify the website, you need `hugo` and `git` installed on your
computer. If Hugo isn't available in your package manager, obtain it from its
[official website](https://gohugo.io). We tested the website build with Hugo
from version 0.20.7 upwards. Please make sure that you use an as recent version
as possible to avoid errors.


### Getting involved

First of all, you'll need an account on [github.com](https://github.com) and become a FOSSASIA
[member here](https://orgmanager.miguelpiedrafita.com/o/fossasia).


You can now clone the repo, open issues and make pull requests to solve issues.


## Translate

Read through [TRANSLATE.md](/TRANSLATE.md) to contribute to the localization of the site.


## Build

To see a preview of the website you need to have Hugo installed and be able to
execute Bash scripts in your command line.

1. Navigate to the website's root directory (e.g. `~/PMPC/website/`) and open a terminal window there. Type in
   `git pull`. This will get the latest changes from the server 
2. In the terminal, execute `cd site/` to navigate in the right directory for hugo's website build. 
3. Only if you added a new languages which doesn't exist on the website yet: Add you 2-letter language code in line 4 of the [build.sh
   file](./pmpc/website/src/master/site/build/build.sh#L4).
4. In your terminal, execute `./build/build.sh server`. This command will build the website and enable you to browse the result on your computer only. Open [localhost:1313](http://localhost:1313/) in your web  browser to see it.


## HowTos and FAQs 

### Important file paths

The website structure is very easy. The most important files and directories are:

- `site/config-static.toml`: Static texts and URLs which are the same for any language
- `site/languages/strings.{en,fr...}.toml`: Headlines, site title, many texts for the various languages.
- `site/content`: Markdown-files for sub-pages like /openletter, can be translated
- `site/data/{en,de...}/share`: Services and their very short translatable strings where people can share to. Is being used in the "Spread" section and the left-side sharing icons
- `site/static/`: CSS, images, and Javascript files for the design.
- `site/static/css/custom.css`: File where all custom CSS code should be written to.
- `site/layouts/`: HTML structure (scaffold) for the website. Useful if you want to add another section or modify anchor links or CSS classes.
- `site/layouts/page`: Template for a sub-page like /privacy
- `site/layouts/shortcodes`: HTML/Hugo code which can be important from within a Markdown file
- `site/public/`: Built files which are used to display the website. Generated by running `hugo`.


### Add a new supporting organisation

Adding a new supporting organisation requires two steps:

1. Add a new entry in [site/data/organisations/organisations.json](./pmpc-website/src/improve-readme/site/data/organisations/organisations.json) in valid JSON format, the file should be self-explaining: *name* is the full name of the organisation, *img* is the name of the logo file (case-sensitive!), and *url* the web address of the organisation. To make sure that the file has a valid JSON syntax you can use [jsonlint.com](https://jsonlint.com/) or another tool before committing your changes.
2. Add the organisation's logo to the [site/static/img/organisations](./pmpc-website/src/improve-readme/site/static/img/organisations) directory. Please only upload PNG files with maximum 150px width or 100px height – ideally using transparency instead of white as background so we can also use it on other backgrounds some day. Consider using `pngcrush` or a similar tool to reduce the file's size and remove metadata.


### Travis Build

We are using Travis to automatically build the website. The site is automatically deployed when there's a push to the master branch of the repository.


## Licence

This site is based on the website publiccode.eu of the Free Software Foundation Europe e.V. Software applications are all free software and used under the respective licenses. The site itself is Copyright 2017 by the FSFE, FOSSASIA and its contributors and licensed under the GPLv3 license.

