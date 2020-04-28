# OS2Core

This is a Drupal 8 basic installation profile for an OS2 Drupal project.

## Usage

### Composer

Use [drupal-composer project](https://github.com/drupal-composer/drupal-project) to fetch drupal core and os2web profile with contribution modules and their dependencies.

Example:
```
composer create-project drupal-composer/drupal-project:8.x-dev [your_project_name] --no-interaction
cd [your_project_name]
composer require os2come/os2core
drush si os2core --db-url=mysql://db_user:db_pass@mysql_host/db_name--locale=da --site-name="OS2Core Drupal project" --account-pass=admin -y
```

### Installation profile

The installation profile only enables commonly used ui modules. It is up to the developer to decide which of the supplied OS2Web modules are needed. These can be enabled from the "Modules" page, otherwise they can be removed.
