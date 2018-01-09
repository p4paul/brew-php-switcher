Brew PHP Switcher [![Build Status](https://travis-ci.org/philcook/brew-php-switcher.svg?branch=master)](https://travis-ci.org/philcook/brew-php-switcher)
=========

Brew PHP switcher is a simple script to switch your Apache and CLI configs quickly between major versions of PHP.

If you support multiple products/projects that are built using either brand new or old legacy PHP functionality and you find it a pain to change config files continually this will make the whole process just one command.

Caveats
-------

For users of OSX only who have installed PHP via [Homebrew] and for PHP version 5.3, 5.4, 5.5, 5.6, 7.0, 7.1 and 7.2 only.

Your Apache config must have native osx PHP module commented out.
```sh
#LoadModule php5_module libexec/apache2/libphp5.so
```

Brew PHP Switcher will automatically add the [Homebrew]'s PHP module location in the Apache config in the following format.
```sh
LoadModule php5_module /usr/local/opt/php53/libexec/apache2/libphp5.so
LoadModule php5_module /usr/local/opt/php54/libexec/apache2/libphp5.so
LoadModule php5_module /usr/local/opt/php55/libexec/apache2/libphp5.so
LoadModule php5_module /usr/local/opt/php56/libexec/apache2/libphp5.so
LoadModule php7_module /usr/local/opt/php70/libexec/apache2/libphp7.so
LoadModule php7_module /usr/local/opt/php71/libexec/apache2/libphp7.so
LoadModule php7_module /usr/local/opt/php72/libexec/apache2/libphp7.so
```

Version
----

1.7

Installation
--------------
```sh
brew tap homebrew/php
brew install brew-php-switcher
```

Where **56** exists, please replace with syntax of **53**, **54**, **55**, **56**, **70** or **71** or **72** depending on which version is required.
```sh
brew-php-switcher 56
```

> by default will switch apache config

Options
--------------

- `-s|-s=*` Skips apache & valet config switch for i.e

```sh
# skip apache only
brew-php-switcher 56 -s

# skip valet only
brew-php-switcher 56 -s=valet

# skip valet & apache
brew-php-switcher 56 -s=valet,apache
```
- `-c=*` switch a specific config for i.e

```sh
# switch valet config only
brew-php-switcher 56 -c=valet

# switch valet & apache config only
brew-php-switcher 56 -c=valet,apache

# switch apache config only
brew-php-switcher 56 -c=apache
```

License
----

MIT

[Homebrew]:http://brew.sh/
[@p_cook]:http://twitter.com/p_cook
