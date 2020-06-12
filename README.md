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

The installation profile only enables commonly used ui modules. It is up to the developer to decide which of the supplied OS2Core modules are needed. These can be enabled from the "Modules" page, otherwise they can be removed.

## Export translations
Get latest db dump from production environment.
Make sure that you have set up correct translation folder.

Check in your `settings.php`
```
$settings['custom_translations_directory'] = 'profiles/contrib/os2core/translations';
```
Run export translation command:
```
drush language-export --langcodes=da --file=os2core-drupal-8.x.da.po
```
## Update translations

```
git pull
sh profiles/contrib/os2core/scripts/translations-update.sh
```
Script includes following steps:
- dumping current translations to `./translations/translation-dumps` directory
- import current version of translation file


After export all changes should be reviewed and commited.
