# Blueprint Function Library

The Blueprint Function Library contains shared functions for Crowdbotics Blueprints.

## Creating a new Blueprint

See [the Blueprint template repo](https://github.com/crowdbotics/blueprint-template)
for instructions on creating a new Blueprint.

## Using This Library

Each file contains functions for a specific language and/or framework. `source`
these files in your `install.sh` script. See the relevant file for available
functions.

## Guidelines

These are the guidelines for adding additional functionality to this library.

1. Blueprints must include a bash script named "install.sh". This file makes all changes needed to install the component into the project.
1. The only available utilities are those installed with Alpine Linux.
2. Scripts must be bash. No other languages should be used. Other interpreters,
   such as python, are not available.
3. All code must be idempotent.

### install.sh

install.sh receives the following arguments:

1. The full path to the project defined as `BASE_PATH`. It must be used when defining the paths to other files.
2. The name of the project in slug format defined as `APP_NAME`. This may be used in paths, such as the app name in a Django project.

The install script may not modify anything outside of `BASE_PATH`. The rest of the file system should be considered ephemeral.
