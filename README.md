Generating Pywikibot packages
=============================

The **Pywikibot-nightly-creator** is a script used for creating nightly builds of the
*[Pywikibot](https://doc.wikimedia.org/pywikibot/stable/)* framework which are published at
https://pywikibot.org.

*Pywikibot* is a Python library that provides tools for interacting with *MediaWiki* wikis, such as
*Wikipedia*.

| Script | Description |
|-|-|
| ``pre_nightly`` | clones https://github.com/pywikibot/Pywikibot-nightly-creator into ``nightly-source`` folder |
| ``nightly-source/nightly`` | creates ``public_html`` folder from ``public_html_static`` folder and clones all the packages into it |

crontab runs these files every 12 hours. It is backed up in ``crontab.bak``file.
You can edit ``index.html`` in ``public_html_static`` folder, which will be deployed in
12 hours. It creates the followings:

| Type | Name | Description
|-|-|-|
| folder | ``public_html`` | the output to web service
| folder | ``public_html.old`` | temp, you can remove it freely
| file | ``pre_nightly.out``\|``.err`` | output from cloning nightly-source repo
| file | ``nightly.out``\|``.err`` | output from creating public_html folder
