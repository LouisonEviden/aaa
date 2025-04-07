# Introduction

This repository is a template to generate a DBT project with a Snowflake database with preset Github Actions.

# Installation

`git clone https://github.com/...`

Add a Github Action secret named `SNOW_PASSWORD` with the snowflake password of your account.

# Usage

## For a developer

Copy the content of [`profiles.yml`](./profiles.yml) into your local `profiles.yml` and set your Snowflake dev schema by replacing `<AAA>` with your trigram (Example: Marc Paul -> MPL).

# Information

This template use these schemas to build DBT pipelines :
- RAW
- Bronze
- Silver
- Gold

It also use github action to automate test and model refresh :
- [merge-dbt-run.yml](./.github/workflows/merge-dbt-run.yml) : Refresh the snowflake data model and refresh the DBT docs on a Github Page.
- [pr-dbt-test.yml](./.github/workflows/pr-dbt-test.yml) : Run DBT test on a dedicated test environment when a pull request is created/updated.
