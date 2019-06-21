# Egeniq Coding Standard
The Egeniq Coding Standard is a set of [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer) rules that we
use at Egeniq. The standard is heavily based on [Doctrine Coding Standard](https://github.com/doctrine/coding-standard/).

# Installation
You can install the Egeniq coding standard as a composer dependency to your particular project. Just run the following 
command to add it to your project:

```
php composer require --dev doctrine/coding-standard
```

Then you can use it like:

```
vendor/bin/phpcs --standard=Egeniq /path/to/some/file/to/sniff.php
```

You might also do automatic fixes using phpcbf:

```
vendor/bin/phpcbf --standard=Egeniq /path/to/some/file/to/sniff.php
```

# Project-level ruleset
To enable the Egeniq coding standard for your project, create a phpcs.xml.dist file with the following content:

```xml
<?xml version="1.0"?>
<ruleset>
    <arg name="basepath" value="."/>
    <arg name="extensions" value="php"/>
    <arg name="parallel" value="80"/>
    <arg name="cache" value=".phpcs-cache"/>
    <arg name="colors"/>

    <!-- Ignore warnings, show progress of the run and show sniff names -->
    <arg value="nps"/>

    <!-- Directories to be checked -->
    <file>app</file>
    <file>tests</file>

    <!-- Include full Egeniq coding standard -->
    <rule ref="Egeniq"/>
</ruleset>
```

This will enable verbatim the Egeniq coding standard with all rules included with their defaults. From now on you can just 
run `vendor/bin/phpcs` and `vendor/bin/phpcbf` without any arguments :raised_hands:.

