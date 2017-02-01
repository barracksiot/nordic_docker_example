[![Build Status](https://travis-ci.org/barracksiot/nordic_docker_example.svg?branch=master)](https://travis-ci.org/barracksiot/nordic_docker_example)

## Automated build using Jenkins, Travis, Docker and Nordic code

This repository contains the files for building an example projet using our [Docker image](https://github.com/barracksiot/nrf5_sdk_docker).

### Jenkins

You can build this project, as long as you have the Docker pipeline plugin.

### Travis

You can fork this project and test the Travis integration yourself.

### Example app

The source code comes from Nordic's examples. The only changes were made on the Makefiles in order to allow overrding the SDK location.
