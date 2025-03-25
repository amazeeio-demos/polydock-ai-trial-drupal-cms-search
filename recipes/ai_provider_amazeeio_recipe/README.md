# amazee.io Drupal AI Provider
This recipe will install and configure the amazee.io AI Provider. This recipe
is intended to be used for automated installs in amazee.io's infrastructure.

```shell
# One of the following to install Drupal CMS or Drupal Core:
composer create-project drupal/cms
composer create-project drupal/recommended-project && composer require drush/drush

# Set the minimum stability.
composer config minimum-stability dev

# Install Drupal
drush site:install -y

# Add the recipe to the project and install.
composer require drupal/ai_provider_amazeeio_recipe -W
drush recipe ../recipes/ai_provider_amazeeio_recipe \
  --input=ai_provider_amazeeio_recipe.llm_host={llm_host_name} \
  --input=ai_provider_amazeeio_recipe.llm_api_key={llm_api_key} \
  --input=ai_provider_amazeeio_recipe.postgres_db_host={postgres_host} \
  --input=ai_provider_amazeeio_recipe.postgres_db_port={postgres_port} \
  --input=ai_provider_amazeeio_recipe.postgres_db_username={postgres_username} \
  --input=ai_provider_amazeeio_recipe.postgres_db_password={postgres_password} \
  --input=ai_provider_amazeeio_recipe.postgres_db_default_database={postgres_database}
```

Once the amazee.io recipe is installed, you can then install other recipes as
desired. For example, to install Drupal CMS's AI tools, you can run the
following:
```shell
drush recipe ../recipes/drupal_cms_ai \
  --input=drupal_cms_ai.openai_api_key='' \
  --input=drupal_cms_ai.anthropic_api_key=''
```
_Note: Setting the keys to empty will skip setting up OpenAI/Anthropic._
