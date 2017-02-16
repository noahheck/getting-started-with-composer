# Getting Started with Composer

### Composer

https://getcomposer.org/

![Composer Logo](images/logo-composer-transparent2.png)

(image used under MIT license by https://getcomposer.org)

Composer is a tool for dependency management in PHP. It allows you to declare the libraries your project depends on and will manage (install / update) them for you. Manages packages on a per-project basis. Cross platform - strives for functionality on Windows, Linux and MacOS.



### Requirements

PHP 5.3.2+
git or other vcs to install packages beyond simple zip archives
Few system / php.ini settings (composer will warn about invalid settings)



### Installation

#### Windows / Linux / MacOS / Unix

Find instructions at: https://getcomposer.org/doc/00-intro.md



### Project Setup

Have Composer run through the interactive configuration generator where you define your project and search for dependencies. Creates initial `composer.json`:

```
php /path/to/composer init
```

Add packages to your project. Composer will add an entry for each package to the `require` key of your `composer.json` file:

```
php /path/to/composer require name-of-package [version constraints]
```

Install packages. Package resources are installed in `vendor` directory of project:

```
php /path/to/composer install
```

Commit `composer.json` and `composer.lock` to vcs, but exclude `vendor` directory



### Updating Resources

Update project dependencies:

```
php /path/to/composer update
```

Update Composer:

```
php /path/to/composer self-update
```



### Install vs. Update

`install` command looks for `composer.lock` file and installs dependencies listed there if found - creates new `composer.lock` if not found. `update` installs latest versions of all dependencies and writes to `composer.lock`



### Using Package Resources

`include`/`require` the generated `autoload.php` file in your application:

```php
<?php

include "path/to/vendor/autoload.php";
```

Add project files to Composer autoloader by adding `autoload` key in `composer.json`:

```json
    "autoload": {
        "psr-4": "path/to/project/files"
    }
```



### Finding packages

Visit https://packagist.org/ to find packages

Use Composer to search for packages

```
php /path/to/composer search [search]
```



### Version constraints

Rules for package versioning constraints: https://getcomposer.org/doc/articles/versions.md

Check version constraints at https://semver.mwl.be/
