# FiveJars Drupal quality check package

## Overview

Provides set of libraries to easily setup code quality checks based on [GrumPHP](https://github.com/phpro/grumphp) for Drupal project.

## Install

1. Add this package using composer `composer require --dev fivejars/drupal-quality-check`
2. Copy configuration files(`grumphp.yml.dist`, `phpmd.xml.dist`, `phpstan.neon.dist`) in project's root directory (not Drupal root directory)
without `.dist` suffix(`grumphp.yml`, `phpmd.xml`, `phpstan.neon`).
3. Overview and change configuration according to your project requirements.
4. Copy the scripts section from `composer.scripts.json` to your project `composer.json` or merge it using `wikimedia/composer-merge-plugin`.

That's it. Now, GrumPHP tasks run on every `git commit`.
Also you can to run other tasks using composer scripts.

>*Note:* As part of install, GrumPHP adds `pre-commit` hook to repository. Existing `pre-commit` might get [destroyed](https://github.com/phpro/grumphp/issues/416) when install/uninstall.

## Composer Scripts
1. `composer grumphp` - Run GrumPHP for the project files added to Git
2. `composer phpmetrics` - Generate PHP Metrics for project files from configured directories(see composer.scripts.json in the package root)
3. `composer phpstan` - Run PHPStan for the project files from configured directories(see phpstan.neon in your project root)
4. `composer phpcs YOUR_DIR` - Run PHPCS on the directory from command argument.
5. `composer phpcbf YOUR_DIR` - Run PHPCBF on the directory from command argument.
6. `composer phpmd` - Run PHPMD for the project files from configured directories(see phpmd.xml in your project root)
7. `composer phpmnd` - Run PHPMD for the project files from configured directories(see composer.scripts.json in the package root)
8. `composer twigcs YOUR_DIR` - Run TwigCS on the directory from command argument.

## Features

1. [PHPCS](https://github.com/squizlabs/PHP_CodeSniffer) with Drupal standard.
2. [PHP Lint](http://www.icosaedro.it/phplint/)
3. [YAML Lint](http://www.yamllint.com/)
4. [Composer](https://github.com/composer/composer)
5. [Composer Normalize](https://github.com/ergebnis/composer-normalize)
6. [JSONLint](https://jsonlint.com/)
7. [PHPStan](https://github.com/phpstan/phpstan)
8. [TwigCS](https://github.com/friendsoftwig/twigcs)
9. [PHPCompatibility](https://github.com/PHPCompatibility/PHPCompatibility)
10. [PHPMetrics](https://github.com/phpmetrics/PhpMetrics)

Long list checks/validators available [here](https://github.com/phpro/grumphp/blob/master/doc/tasks.md#tasks-1).
