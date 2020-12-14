> This project is maintained in the [silverback monorepo](https://github.com/AmazeeLabs/silverback-mono)
# Silverback CLI

`amazee/silverback-cli` is a composer package adding tooling and configuration scaffolding to Amazee Drupal projects.

Killer features:
- 🚀 Super-fast Drupal installations. Very useful for automated testing.
- 📸 Create/restore snapshots of Drupal state.

Other features:
- Basic configuration for Lagoon and Lando.
- Some small improvements for the Drupal setup.

## Installation

Make sure you have [all dependencies](https://github.com/AmazeeLabs/silverback-mono#requirements) installed. `direnv` is an important one.

```sh
composer require amazeelabs/silverback-cli
./vendor/bin/silverback init
direnv allow
```

## Usage

```sh
# To quick-start Drupal:
silverback setup
drush serve

# To see other use cases:
silverback list
silverback help [command_name]
```

## How it works

A Drupal project initialized with Silverback uses a SQLite database in development environment. The database is located in the Drupal files directory. This means that the whole Drupal state is stored in a single directory.

Silverback puts this directory into `install-cache.zip` and reuses it the next time `silverback setup` is fired.

Snapshots work in the same way. They are just copies of the Drupal files directory.
