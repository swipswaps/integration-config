# Wikimedia configuration for Jenkins

This repository holds the configuration of the Wikimedia Foundation Inc. Jenkins
jobs. It is meant to be used with a python script written by the OpenStack
Foundation: Jenkins Job Builder.

When you tweak or add jobs, follow the documentation maintained on mediawiki.org:

  https://www.mediawiki.org/wiki/CI/JJB

For more about the Jenkins Job Builder software and how to use it, refer to the upstream documentation:

  https://docs.openstack.org/infra/jenkins-job-builder/

## Example Usage

You should run Jenkins job builder using:

    $ tox -e jenkin-jobs -- <arguments>

Generate XML files for Jenkins jobs from YAML files:

    $ tox -e jenkins-jobs -- test ./jjb/ -o output/

Update Jenkins jobs which name starts with "selenium":

    $ tox -e jenkins-jobs --conf jenkins_jobs.ini update ./jjb/ selenium*

## Running tests

To test the configuration, we use tox and you need at least version 1.9+ ([bug T125705](https://phabricator.wikimedia.org/T125705))
to run the test suite. Running `tox` in the main dir of your local clone runs the tests.

## Whitelist volunteer users

https://www.mediawiki.org/wiki/Continuous_integration/Whitelist
