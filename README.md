# Quick start

Clone the repository

Copy `blt/example.local.blt.yml` to `blt/local.blt.yml` and adjust your database settings in your `blt/local.blt.yml` file.
and set in it:
```
drupal:
  db:
    database: drupal9
    username: drupal9
    password: drupal9
    host: database
    port: 3306
```

```
cd c-kickstarter
lando start
lando composer install
./vendor/bin/blt source:build:settings
./vendor/bin/blt setup
```

if you have some issues with importing SQL dump:

```
lando db-import dump/dump.sql
```


If you have issues with building token.css file change string in yarn.lock
postcss-preset-env "^6.7.0" to "7.2.3"

run 
```
yarn upgrade postcss-preset-env@7.2.3
```

# Wingsuit Kickstarter
See the [documentation](https://wingsuit-designsystem.github.io/drupal/ui_patterns/) for more details.

## Prerequisites

- [Node `^12`](https://nodejs.org)
- [YARN `^1.22`](https://classic.yarnpkg.com/)
- [PHP `^7.0.0`](https://php.net)

## Quickstart
```
composer create-project vas-speedandfunction/c-kickstarter c-kickstarter --stability dev --no-interaction
```
Copy `blt/example.local.blt.yml` to `blt/local.blt.yml` and adjust your database settings in your `blt/local.blt.yml` file.

After that run:
```
blt source:build:settings
blt setup
```


## Docksal Quickstart
```
fin rc -T composer create-project wingsuit-designsystem/wingsuit-kickstarter wingsuit-kickstarter --stability dev --no-interaction
cd wingsuit-kickstarter && fin init
```
To start storybook inside docksal:
```
cd docroot/themes/custom/wingsuit
fin exec yarn dev:storybook:docksal
```
and open http://storybook.wingsuit-kickstarter.docksal


## Develop Wingsuit only: Link `Wingsuit` to `Wingsuit Kickstarter`
Use this mode to link `https://github.com/wingsuit-designsystem/wingsuit` as volume.

   * Create a folder `wingsuit`
   * Clone "https://github.com/wingsuit-designsystem/wingsuit" and this repository inside `wingsuit`
   * Run `export DOCKSAL_ENVIRONMENT=docksal-dev`
   * Check the `WINGSUIT_PATH` in `.docksal/docksal-docksal-dev.env`
   * run `cd wingsuit-kickstarter && fin init`
