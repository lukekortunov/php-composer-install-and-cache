# PHP Composer action

This action simply install PHP dependencies via Composer and uses `actions/cache@v2` under the hood to speed up deployments.

# Usage

## Pre-requisites

Create a workflow `.yaml` file in your repository under `.github/workflows` directory. [Example](#example-workflow) of workflow is available below

## Inputs

n/a

## Outputs

n/a

## Example workflow

```yaml
name: Run tests on PHP application

on: pull_request

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
        - name: Checkout on current commit
          uses: actions/checkout@v2
        
        - name: Install PHP dependencies
          uses: lukekortunov/php-composer-install-and-cache@v1

        - name: Run tests
          run:  php vendor/bin/phpunit
```
