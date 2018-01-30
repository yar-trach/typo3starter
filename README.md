# typo3starter [![TYPO3](https://img.shields.io/badge/TYPO3-8.7.9-orange.svg?style=flat-square)](https://typo3.org/)
> Starter for TYPO3 site (TYPO3 8 + mysql 5.7)

![image](https://bytebucket.org/snippets/yar-trach/ReyE59/raw/f79a916820cfc9db4a5284a337f8bd10c8d89493/section_starter-lines.svg)

# How to start
Clone this project into your folder (in this case it will clone project into **new-project** folder; you should change this folder name to avoid misunderstanding what project you working with):
```sh
$ git clone git@github.com:yar-trach/typo3starter.git new-project
// Cloning project into ./new-project folder
$ cd new-project
```
Now, install requirements:
```sh
$ composer install
```
After all of this is done successfully, build and make up Docker images:
```sh
$ docker-compose up -d
```

# Where to find local site?
**Local installation** of site you can find by typing in browser:
```sh
http://localhost:8080
```
**Solr** can be found:
```sh
http://localhost:8983
```
Also, you can open **phpMyAdmin** on:
```sh
http://localhost:8181
```