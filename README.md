# maven deploy github action

[![License](https://img.shields.io/github/license/eitco/bom-maven-plugin.svg?style=for-the-badge)](https://opensource.org/license/mit)


This github action starts a maven build. It is a [composite action](https://docs.github.com/en/actions/creating-actions/creating-a-composite-action) 
that:

1. checks out the repository source code
    * using the [default checkout action](https://github.com/actions/checkout)
2. sets up a jdk and maven
    * using the [default setup-java action](https://github.com/actions/setup-java) 
3. executes maven
   1. if the user is dependabot `mvn install` will be called
   2. otherwise `mvn deploy` will be called

The action can be customized using the following parameters:

## java-version
The (major) version of the jdk.

default: **17**

## java-distribution
The jdk distribution

default: **temurin**

## gpg-private-key
The gpg private key to use for artifact signing. Make sure to use a github secret here. 

## gpg-key-name
The name of the gpg private key. Consider using a github secret here.

## gpg-passphrase
The passphrase of the gpg private key. Make sure to use a github secret here.

## deploy-user
The user to authenticate at the artifact repository. Consider using a github secret here.

## deploy-password
The password to authenticate at the artifact repository. Make sure to use a github secret here.