# TutleBuild/aws-cli

## Description
* This docker image is based on [aws-cli](https://hub.docker.com/r/amazon/aws-cli) and with the following components:
    * jdk17
        * [Gradle 7.4.2](https://docs.gradle.org/current/userguide/userguide.html)
        * [Amazon Corretto 17](https://docs.aws.amazon.com/ja_jp/corretto/latest/corretto-17-ug/what-is-corretto-17.html)
    * jdk11
        * [Gradle 6.8.3](https://docs.gradle.org/6.8.3/userguide/userguide.html)
        * [Amazon Corretto 11](https://docs.aws.amazon.com/ja_jp/corretto/latest/corretto-11-ug/what-is-corretto-11.html)

## Build
**jdk17**
```sh
docker build -t turtlebuild/aws-cli:gradle7.4.2-jdk17 ./jdk17
```

**jdk11**
```sh
docker build -t turtlebuild/aws-cli:gradle6.8.3-jdk11 ./jdk11
```