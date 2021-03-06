# LESS Helper

## Requirements

LESS CSS parser (http://github.com/cloudhead/less.js) installed with Node.js on the server your site will run on. The command for this parser is in the extension.driver.php file. If you choose another LESS parser, please change the command.

As this extension uses the `lessc` executable to do the conversion you'll need to make sure PHP has access to the `lessc` executable or its alias. If the extension isn't working for your out-of-the-box, try setting the `$less_exec` variable at the top of `extension.driver.php` to the full path to the `lessc` executable. It'll be something like `/usr/local/bin/lessc`, you should be able to find out by typing `which lessc` into the shell on your server.
## Installation
 
1. Upload the `less_helper` folder in this archive to your Symphony `extensions` folder.
1. Enable it by selecting the "LESS Helper", choosing "Enable" from the  with-selected menu, then clicking "Apply".
1. Links to `.less` files in your templates will now be automatically converted to CSS.

## Usage

To use the Sass Helper you simply need to point your CSS includes to your `.less` instead of `.css`. The extension will automatically find them and generate a `.css` file in the same directory. For example, this:

    <link href="{$workspace}/assets/less/screen.less" media="screen, projection" rel="stylesheet" type="text/css" />

Will be output as:

    <link href="http://domain.com/workspace/assets/css/screen.css?mod-1248022788" media="screen, projection" rel="stylesheet" type="text/css" />
