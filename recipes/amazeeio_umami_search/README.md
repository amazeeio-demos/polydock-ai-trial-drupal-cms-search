# amazee.io Umami Search

This recipe will add an AI powered search to the Umami demo to demonstrate the capabilities of AI search.

## How to use
Compare the search results between the traditional search (header) and the AI search (sidebar).

## Adding to an existing project

#### Requirements
1. An Unami installation.
2. The [amazee.io AI provider](https://www.drupal.org/project/ai_provider_amazeeio) configured.

#### Installation
The database name can be retreived from the amazee.io AI provider configuration page.
```shell
composer require drupal/amazeeio_umami_search
drush recipe ../recipes/amazeeio_umami_search \
  --input amazeeio_umami_search.postgres_db_default_database={database}
drush cr
```

## Quick start project with the amazee.io AI provider
```shell
composer create-project drupal/recommended-project:^11
composer config minimum-stability dev
composer require drupal/ai_provider_amazeeio drupal/amazeeio_umami_search

drush site:install demo_umami
drush en ai_provider_amazeeio
# Configure the provider via the UI and note the database name.
drush recipe ../recipes/amazeeio_umami_search \
  --input amazeeio_umami_search.postgres_db_default_database={database}
drush cr
```
