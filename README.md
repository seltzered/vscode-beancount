# Beancount

Simple Beancount support for VSCode

[![version](https://vsmarketplacebadge.apphb.com/version/Lencerf.beancount.svg)](https://marketplace.visualstudio.com/items?itemName=Lencerf.beancount)
[![installs](https://vsmarketplacebadge.apphb.com/installs-short/Lencerf.beancount.svg)](https://marketplace.visualstudio.com/items?itemName=Lencerf.beancount)
[![license](https://img.shields.io/badge/license-MIT-brightgreen.svg)](https://raw.githubusercontent.com/Lencerf/vscode-beancount/master/LICENSE.txt)


## Features

1. Syntax highlight (syntax file from [draug3n/sublime-beancount](https://github.com/draug3n/sublime-beancount/blob/master/beancount.tmLanguage))
2. Decimal point alignment
3. Insert current Date
4. Auto check after saving
5. Code snippets ([@vlamacko](https://github.com/Lencerf/vscode-beancount/pull/7))

## Extension Settings

This extension contributes the following settings:

* `beancount.separatorColumn`: specify the column of the decimal separator.
* `beancount.instantAlignment`: Set it to `true` to align the amount (like 1.00 BTC) once a decimal point is inserted.
* `beancount.mainBeanFile`: If you are splitting beancount files into multiple files, set this value to either the full path or the relative path to your main bean file so that
this extension can get all account information. If it is left blank, the extension will consider the file in the current
window as the main file.
* `beancount.runFavaOnActivate`: If it is set to `true`, fava will run once this extension is activated.

## Best practice

Split your ledger into several `.bean` files according to time or accounts and 
put all your `open`/`close` in a main file. Include all other files in the 
main file by the `include` command. For example, the file structure looks like this
```
BeanFolder
├── main.bean
├── before2017.bean
├── 2017-01.bean
└── 2017-02.bean
```
Open `BeanFolder` with VSCode and set `beancount.mainBeanFile` to the path of `main.bean` in the current [Workspace Settings](https://code.visualstudio.com/docs/getstarted/settings).

## Known Issues

see GitHub [issue page](https://github.com/Lencerf/vscode-beancount/issues)

## Release Notes

### 0.2.3
* Correctly handle terminal-close event.

### 0.2.2
* Fix some potential bugs;
* `beancount.mainBeanFile` now cen be set to either a relative path or a full path. ([@robotkid](https://github.com/Lencerf/vscode-beancount/pull/10))

### 0.2.1
* Fix a bug related to an empty contentChanges array. ([@robotkid](https://github.com/Lencerf/vscode-beancount/pull/9))
