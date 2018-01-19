# Feedme Vagrant

A development vagrant environment that hosts the feedme dynamic website backed by the hunger app microservice for local development purposes. 

> Note, the environment is currently configured to run on a bridge network so that it will be available to all devices running on the local area network. It assumes that the local router runs on the `192.168.1.x` subnet and will allow a new device to attach to `192.168.1.17`.

## Usage

First make sure you've installed [feedme-vagrant-base](https://github.com/feedmejefferson/feedme-vagrant-base), then _just_ clone this repo and run:

    vagrant up

> Note, I say "just clone this repo", because there are a few other assumptions/dependencies that need to be satisfied before you can run this. Currently it's configured for local development and expects that you've cloned the static site repo, images and hunger app repos and locally built the hunger app output in a specific set of directories. See dependencies below.

## Dependencies

The current configuration expects that the parent directory will contain three additional folders and that the hunger app will have been built/packaged with maven:

* [`site`](https://github.com/feedmejefferson/feedmejefferson.github.io)
* [`images`](https://github.com/feedmejefferson/images)
* [`hunger`](https://github.com/feedmejefferson/hunger)

```
cd ..
git clone git@github.com:feedmejefferson/feedmejefferson.github.io.git site
git clone git@github.com:feedmejefferson/images.git
git clone git@github.com:feedmejefferson/hunger.git
cd hunger
mvn install
```
