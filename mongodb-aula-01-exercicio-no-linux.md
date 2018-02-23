# MongoDB - Aula 01 - Exercício
autor: JÔNATAS FILIPE VIEIRA
OS: Linux Mint 18

## Importando os restaurantes

  ```
  jonatas@jonatas-VM ~/Documentos/projects/be-mean-modulo-mongodb/exercicio1 $ mongoimport --db be-mean --collection restaurantes --drop --file restaurantes.json
  2018-02-23T00:24:59.579-0300    connected to: localhost
  2018-02-23T00:24:59.589-0300    dropping: be-mean.restaurantes
  2018-02-23T00:25:00.882-0300    imported 25359 documents
  ```

## Contando os restaurantes

  ```
  jonatas@jonatas-VM ~/Documentos/projects/be-mean-modulo-mongodb/exercicio1
  $ mongo be-mean
  MongoDB shell version v3.4.13
  connecting to: mongodb://127.0.0.1:27017/be-mean
  MongoDB server version: 3.4.13
  Mongo-Hacker 0.0.14
  jonatas-VM(mongod-3.4.13) be-mean> show dbs
  admin   → 0.000GB
  be-mean → 0.005GB
  local   → 0.000GB
  jonatas-VM(mongod-3.4.13) be-mean> db.restaurantes.find({}).count()
  25359
  ```
