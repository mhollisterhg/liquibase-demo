# Liquibase


# TODO:
- Look into if we can manage functions with Liquibase

---

Database is already correct, but liquibase thinks changes haven't been applied
- liquibase --changeLogFile=master-changelog.yml changelogSync

checksums changed but the changesets are valid
- liquibase --changeLogFile=master-changelog.yml clearCheckSums



# Best Practices

- never modify an applied changeset, only create new ones


# Dev / staging / prod
## dev
- set default schema and connection schema to same thing
  - need to figure out how to interpolate into `liquibase.command.url` (if we even can?)
  - Maybe for dev, everyone just generates their own `dev.liquibase.properties` file via a template or something?

## staging / prod
- set connection schema to `liquibase` or something

# Installing and setting up Liquibase 5.0.1

## Installing Java 17
This version of liquibase requires Java 17. Recommended tool is sdkman. If you have that installed...
```commandline
sdk install java 17.0.17-amzn
sdk use java 17.0.17-amzn

# alternatively...
sdk default java 17.0.17-amzn
```

## Installing Liquibase
As of writing this, version 5 is not yet on Brew. Follow install instructions here: https://docs.liquibase.com/community/get-started-5-0/install-liquibase-on-macos

## Installing the Liquibase Package Manager
This ships by default with Liquibase 5. Simply run
```commandline
liquibase lpm
```
to install it, then
```commandline
lpm <command>
```
to use it

## Installing Databricks plugins
The `liquibase.json` file determines the plugins that will be installed. Simply run

```commandline
lpm install
```
to install them into your local project.

# Other stuff

Currently using JDBC `2.7.4` because `liquibase-databricks` isn't updated for JDBC `3.0.1` yet
- I have an open PR to add support https://github.com/liquibase/liquibase-databricks/pull/332
