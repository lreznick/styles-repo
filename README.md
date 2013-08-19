Installation
------------

    cp include/config.inc.php-sample include/config.inc.php

    cd scripts

Extract Trang binary to current directory:

    wget http://jing-trang.googlecode.com/files/trang-20081028.zip
    unzip -ej trang-20081028.zip trang-20081028/trang.jar
    rm trang-20081028.zip

Install other prerequisites:

* apache2
* php5, php5-curl
* java
* xmllint (part of libxml2-utils package)
* [citeproc-node](https://github.com/zotero/citeproc-node)

Configure apache2

* In addition to the default setup, the following modules must be enabled:
  * mod_rewrite
  * mod_expires
* Apache must be configured to allow overrides of the following options in .htaccess
  * MultiViews

Run setup scripts:

    ./fetch-schema
    ./generate-index
    ./generate-previews

Set generate-index and generate-previews to run periodically via cron.

The main page for the style repository is "/htdocs/styles.php". Configure paths and citeproc URL in "/include/config.inc.php"
