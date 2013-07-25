# ProcessWire2.+ Minify 1.0.3

This module helps you combine Javascript and CSS files into one, minified file to save on unnecessary HTTP requests and to compress files anywhere up to 80% (including already minified .js files).

To use it, extract the attached zip file into your /site/modules/ directory and check for new modules in the ProcessWire Admin area, then install the module.

Once installed, go to configure the module and, instead of this configuring anything for you, you can use the drop-down lists to build stylesheet and script code to place in your templates, grabbing a list of any stylesheets and scripts it finds in the /site/template/styles/ and /site/templates/scripts/ directories respectively.

It's more of a helper than anything else, but it should take the guesswork out of configuring Minify for your site.

*Full details of this module are available here: http://modules.processwire.com/modules/minify/*

__Notes:__

* This module contains a third-party library - Minify - which is subject to its own license (a copy is included in the attached zip file). I've left the module in-tact including its unit test files so there are more files than are necessary, but this will make it easier for me to upgrade the module if/when they release updates to that code.
* This module doesn't insert any code into your templates automatically - I think copying and pasting the code it currently outputs to the screen is more useful/configurable for more situations.
* It's worth using even if you only have one CSS or JS file as it will compress CSS files by about 80% and JS files by quite a lot too, plus since it handles caching on the server-side and does its own checks of the files it is serving (plus it's a dynamic URL), you can always be sure that it will serve the latest version of a CSS file (no more CTRL+F5 to show the new styles if your browser decides to cache it.
* You can change the /site/modules/Minify/min/config.php as you could if you were using Minify as a standalone script - tweak cache paths (default is your server's cache path) and other advanced settings here.

__Updates:__

* v0.0.2 - now produces code that includes paths derived by ProcessWire at run-time so paths will be fine on localhost and live servers, removing potential issues when pushing a site live.
* v1.0.0 - bumped this up to a major version number since there appear to be no issues with the initial versions to speak of. Also implemented yellowled's input field suggestion (looks much better and easier to select for copy and paste purposes) and turned off autoload at ryan's suggestion.
* v1.0.1 - now recusrively searches for files inside subfolders under the scripts and styles directories using PHP 5's built-in iterator classes
* v1.0.2 - pull request from teppo - https://github.com/Notanotherdotcom/Minify/pull/1
* v1.0.3 - updated Minify code to v2.1.7 which fixes a significant security flaw: https://groups.google.com/forum/#!msg/minify/cpN-ncKPFZE/kwYVpLMkfDwJ