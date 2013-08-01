# Social Sharing Privacy for TYPO3

EXT:social_sharing_privacy


## What is this Repo about

This awesome tool is built up on panzi's awesome jQuery Plugin. It supports so many sharing services:

Supported services:

* buffer
* delicious
* disqus
* facebook
* flattr
* gplus
* hackernews
* linkedin
* mail
* pinterest
* reddit
* stumbleupon
* tumblr
* twitter
* xing

Take a loot by yourself: https://github.com/panzi/SocialSharePrivacy.


## Installation

### Via Git

Clone into typo3conf/ext/

	git clone git@github.com:sotastudio/TYPO3.Extbase.SocialSharingPrivacy.git /path/to/project/typo3conf/ext/social_share_privacy/

Install via Extension Manager as usual.

### Via TER

[Jump to TER](http://typo3.org/extensions/repository/view/social_sharing_privacy)


## Configuration

* Include **static Extension Template**
* Grab this Plugin via TS (Library) or Frontend Plugin
* Check the Frontend!


### TypoScript Constants

	plugin.tx_socialsharingprivacy {
    	view {
    		templateRootPath = EXT:social_sharing_privacy/Resources/Private/Templates/
    		partialRootPath = EXT:social_sharing_privacy/Resources/Private/Partials/
    		layoutRootPath = EXT:social_sharing_privacy/Resources/Private/Layouts/
    	}
    	settings {
     		lib {
    			jQuery = EXT:social_sharing_privacy/Resources/Public/Js/jquery-1.9.1.min.js
    			jQueryCookies = EXT:social_sharing_privacy/Resources/Public/Js/jquery.cookies.js
    			moveToFooter = 1
     		}
    	}
    }


### TypoScript Setup

	plugin.tx_socialsharingprivacy {
		view {
			templateRootPath = {$plugin.tx_socialsharingprivacy.view.templateRootPath}
			partialRootPath = {$plugin.tx_socialsharingprivacy.view.partialRootPath}
			layoutRootPath = {$plugin.tx_socialsharingprivacy.view.layoutRootPath}
		}
		settings {
			lib {
				jQuery = {$plugin.tx_socialsharingprivacy.settings.jQuery}
				jQueryCookies = {$plugin.tx_socialsharingprivacy.settings.jQueryCookies}
				moveToFooter = {$plugin.tx_socialsharingprivacy.settings.moveToFooter}
			}
			# Leave empty to share dynamic urls of the pages the visitor is visiting.
			uri =
			# Choice of design: line|box
			layout = line
			# To obtain perma settings: 1|0
			useCookies = 1
			# Csv of used serviced - dont use whitespace between them.
			# Possible values: buffer,delicious,disqus,facebook,flattr,gplus,hackernews,linkedin,mail,pinterest,reddit,stumbleupon,tumblr,twitter,xing
			services = facebook,twitter,gplus,xing
		}
	}


### Miscellaneous

Take a look at

* /Configuration/Typoscript/constants.txt
* /Configuration/Typoscript/setup.txt

to get further infos about settings and language labels.


## How to

### … use the Plugin in a Library

… to e.g. refer it to the page template:

	lib.example < temp.socialSharingPrivacy
	lib.example.settings.services = facebook,twitter,gplus

You are instantly ready to go - Of course you can adjust the TypoScript Setup to fit your need via lib.example.settings.
Just dig into /Configuration/Typoscript/setup.txt to get a clue about the possibilities.


## Roadmap and Tasks

Make it configurable via Flexform (Content Element/Frontend Plugin) - currently you run best by copying it via TS.


## Contribute

If you have ideas or other kind of feedback, don't hesitate and let me know!

Feel also free to fork and pull.