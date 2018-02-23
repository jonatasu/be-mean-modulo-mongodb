# MongoDB - Aula 01 - Exercício
autor: JÔNATAS FILIPE VIEIRA
OS: Windows 10

## Importando os restaurantes

  ```
  jonat@DESKTOP-B4J26G4 MINGW32 ~/OneDrive/Documentos/BeMEAN/exercicio1
  $ mongoimport --db be-mean --collection restaurantes --drop --file restaurantes.json
  2018-02-06T23:10:59.389-0200    connected to: localhost
  2018-02-06T23:10:59.450-0200    dropping: be-mean.restaurantes
  2018-02-06T23:11:01.300-0200    [#########...............] be-mean.restaurantes 4.64MB/11.3MB (40.8%)
  2018-02-06T23:11:01.947-0200    [########################] be-mean.restaurantes 11.3MB/11.3MB (100.0%)
  2018-02-06T23:11:01.947-0200    imported 25359 documents
  ```

## Contando os restaurantes

  ```
  jonat@DESKTOP-B4J26G4 MINGW32 ~/OneDrive/Documentos/BeMEAN/exercicio1
  $ mongo
  MongoDB shell version v3.6.2
  connecting to: mongodb://127.0.0.1:27017
  MongoDB server version: 3.6.2
  db
  test
  show dbs
  admin    0.000GB
  be-mean  0.005GB
  config   0.000GB
  local    0.000GB
  use be-mean
  switched to db be-mean
  db
  be-mean
  db.restaurantes.find({}).count()
  25359
  ```
