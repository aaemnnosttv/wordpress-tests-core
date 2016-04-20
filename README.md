# WordPress Tests Core

WordPress Core PHPUnit Test Library made installable via Composer!
 
## Usage

Example project's `composer.json`
```
{
    "require": {
        "johnpbloch/wordpress": "*"
    },
    "require-dev": {
        "aaemnnosttv/wordpress-tests-core": "*",
        "phpunit/phpunit": "*"
    },
    "extra": {
        "wordpress-install-dir": "web/wp",
        "wordpress-tests-core-dir": "tests/core"
    }
}
```
> Astrisk versions used for timelessness... You should use a version constraint appropriate for your needs.

#### Example project file structure
```
├── composer.json
├── phpunit.xml
└──  tests
   ├── wp-tests-config.php [REQUIRED]
   └── core
       ├── bootstrap.php
       ├── ...
```
`tests/core` could be any directory, but it must be defined under the `extra` key as shown above. 

#### `wp-tests-config.php`

This file is the equivalent of `wp-config.php` when running your PHPUnit tests.  Due to the limitations imposed by the WordPress core bootstrap.php file, this file *must* be located as a sibling of the directory specified at `wordpress-tests-core-dir` as shown above.

Then you may simply bootstrap PHPUnit with the WordPress core bootstrap file directly.

#### Example `phpunit.xml` excerpt
```
<phpunit
	bootstrap="tests/core/bootstrap.php"
	...
```

#### Other considerations

This package is not a complete replacement for the more commonly known `install-wp-tests.sh` script.  It is just a library.
