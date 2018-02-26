# MongoDB - Aula 02 - Exercício
autor: JÔNATAS FILIPE VIEIRA
OS: Linux Mint 18

## Criar database "be-mean-pokemons"

  ```
  jonatas-VM(mongod-3.4.13) test> use be-mean-pokemons
  switched to db be-mean-pokemons
  jonatas-VM(mongod-3.4.13) be-mean-pokemons>
  ```

## Listagem de databases

  ```
  jonatas-VM(mongod-3.4.13) be-mean-pokemons> show dbs
  admin   → 0.000GB
  be-mean → 0.005GB
  local   → 0.000GB
  pokedex → 0.000GB
  test    → 0.000GB
  ```

## Listagem de coleções em "be-mean-pokemons"

  ```
  jonatas-VM(mongod-3.4.13) be-mean-pokemons> show collections
  jonatas-VM(mongod-3.4.13) be-mean-pokemons>

  ```

## Listagem de coleções em "be-mean-pokemons" após a inserção dos pokémons

  ```
  jonatas-VM(mongod-3.4.13) be-mean-pokemons> show collections
  pokemons → 0.001MB / 0.004MB


  ```

## Listagem dos 5 pokémons inseridos

  ```
  jonatas-VM(mongod-3.4.13) be-mean-pokemons> db.pokemons.find()
  {
    "_id": ObjectId("5a93c3217ba7ca4e3c40bd8c"),
    "name": "Charizard",
    "description": "Charizard flies around the sky in search of powerful opponents.",
    "type": "Fogo",
    "attack": 70,
    "height": 1.7
  }
  {
    "_id": ObjectId("5a93c32b7ba7ca4e3c40bd8d"),
    "name": "Blastoise",
    "description": "Blastoise has water spouts that protrude from its shell. ",
    "type": "Água",
    "attack": 68,
    "defense": 85,
    "height": 1.6
  }
  {
    "_id": ObjectId("5a93c3337ba7ca4e3c40bd8e"),
    "name": "Pidgeot",
    "description": "This Pokémon has a dazzling plumage of beautifully glossy feathers. ",
    "type": "Normal",
    "attack": 67,
    "defense": 69,
    "height": 1.5
  }
  {
    "_id": ObjectId("5a93c33f7ba7ca4e3c40bd8f"),
    "name": "Golduck",
    "description": "The webbed flippers on its forelegs and hind legs and the streamlined body",
    "type": "Water",
    "attack": 76,
    "defense": 73,
    "height": 1.7
  }
  {
    "_id": ObjectId("5a93c3477ba7ca4e3c40bd90"),
    "name": "Arcanine",
    "description": "Arcanine is known for its high speed. It is said to be capable of running",
    "type": "Fogo",
    "attack": 71,
    "defense": 82,
    "height": 1.9
  }
  Fetched 5 record(s) in 121ms
  ```

## Buscar pokémon pelo nome e armazená-lo na variável "poke"

  ```
  jonatas-VM(mongod-3.4.13) be-mean-pokemons> var queryUpdate = {name: 'Charizard'}
  jonatas-VM(mongod-3.4.13) be-mean-pokemons> var poke = db.pokemons.findOne(queryUpdate)
  jonatas-VM(mongod-3.4.13) be-mean-pokemons> poke
  {
    "_id": ObjectId("5a93c3217ba7ca4e3c40bd8c"),
    "name": "Charizard",
    "description": "Charizard flies around the sky in search of powerful opponents.",
    "type": "Fogo",
    "attack": 70,
    "height": 1.7
  }
  ```

## Modificação realizada no pokémon escolhido anteriormente

  ```
  jonatas-VM(mongod-3.4.13) be-mean-pokemons> poke.description = 'Dragãozinho esquentadinho!'
  Dragãozinho esquentadinho!
  jonatas-VM(mongod-3.4.13) be-mean-pokemons> db.pokemons.save(poke)
  Updated 1 existing record(s) in 98ms
  WriteResult({
    "nMatched": 1,
    "nUpserted": 0,
    "nModified": 1
  })
  ```
## Listagem de pokémons após o save()

  ```
  jonatas-VM(mongod-3.4.13) be-mean-pokemons> db.pokemons.find()
  {
    "_id": ObjectId("5a93c3217ba7ca4e3c40bd8c"),
    "name": "Charizard",
    "description": "Dragãozinho esquentadinho!",
    "type": "Fogo",
    "attack": 70,
    "height": 1.7
  }
  {
    "_id": ObjectId("5a93c32b7ba7ca4e3c40bd8d"),
    "name": "Blastoise",
    "description": "Blastoise has water spouts that protrude from its shell. ",
    "type": "Água",
    "attack": 68,
    "defense": 85,
    "height": 1.6
  }
  {
    "_id": ObjectId("5a93c3337ba7ca4e3c40bd8e"),
    "name": "Pidgeot",
    "description": "This Pokémon has a dazzling plumage of beautifully glossy feathers. ",
    "type": "Normal",
    "attack": 67,
    "defense": 69,
    "height": 1.5
  }
  {
    "_id": ObjectId("5a93c33f7ba7ca4e3c40bd8f"),
    "name": "Golduck",
    "description": "The webbed flippers on its forelegs and hind legs and the streamlined body",
    "type": "Water",
    "attack": 76,
    "defense": 73,
    "height": 1.7
  }
  {
    "_id": ObjectId("5a93c3477ba7ca4e3c40bd90"),
    "name": "Arcanine",
    "description": "Arcanine is known for its high speed. It is said to be capable of running",
    "type": "Fogo",
    "attack": 71,
    "defense": 82,
    "height": 1.9
  }
  Fetched 5 record(s) in 2ms
  ```
