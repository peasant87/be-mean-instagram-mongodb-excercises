# MongoDB - Aula 02 - Exercício
autor: Tiago Amaral

## Altura < 0.5

    ```
    db.pokemons.find({height: {$lt: 0.5}})
	{
	  "_id": ObjectId("580fc40aa881fd5358291b7a"),
	  "name": "Diglett",
	  "description": "esconde esconde",
	  "attack": 30,
	  "defense": 10,
	  "height": 0.2
	}
	Fetched 1 record(s) in 2ms

    ```

## Altura >= 0.5

    ```
    db.pokemons.find({height: {$gte: 0.5}})
	{
	  "_id": ObjectId("580fc3f4a881fd5358291b78"),
	  "name": "Sandshrew",
	  "description": "tatu lutador",
	  "attack": 40,
	  "defense": 40,
	  "height": 0.6
	}
	{
	  "_id": ObjectId("580fc3fca881fd5358291b79"),
	  "name": "Clefairy",
	  "description": "fada lutadora",
	  "attack": 20,
	  "defense": 20,
	  "height": 0.6
	}
	{
	  "_id": ObjectId("580fc41fa881fd5358291b7b"),
	  "name": "Abra",
	  "description": "foge-foge da estrela",
	  "attack": 10,
	  "defense": 10,
	  "height": 0.9
	}
	{
	  "_id": ObjectId("580fc427a881fd5358291b7c"),
	  "name": "Tentacool",
	  "description": "polvo lutador",
	  "attack": 20,
	  "defense": 20,
	  "height": 0.9
	}
	Fetched 4 record(s) in 6ms

    ```

## Altura <= 0.5 E tipo = grama

    ```
   var query1 = {type:"grama"}
   var query2 = {height: {$lte: 0.5}}
   db.pokemons.find({$and: [query1, query2]})
	{
	  "_id": ObjectId("580961923ec41a29daaf3196"),
	  "name": "Bulbassauro",
	  "description": "Chicote de trepadeira",
	  "type": "grama",
	  "attack": 49,
	  "height": 0.4
	}
	Fetched 1 record(s) in 2ms

	```

## Nome = "pikachu" OU ataque <= 0.5

    ```
    var query1 = {name:"Pikachu"}
    var query2 = {attack: {$lte: 0.5}}
    db.pokemons.find({$or: [query1, query2]})
	{
	  "_id": ObjectId("580961423ec41a29daaf3195"),
	  "name": "Pikachu",
	  "description": "Rato elétrico bem fofinho",
	  "type": "electric",
	  "attack": 55,
	  "height": 0.4
	}
	Fetched 1 record(s) in 2ms

	```

## Ataque >= 48 E Altura <= 0.5

    ```
	var query1 = {attack:{$gte: 48}}
	var query2 = {height: {$lte: 0.5}}
	db.pokemons.find({$and: [query1, query2]})
	{
	  "_id": ObjectId("580961423ec41a29daaf3195"),
	  "name": "Pikachu",
	  "description": "Rato elétrico bem fofinho",
	  "type": "electric",
	  "attack": 55,
	  "height": 0.4
	}
	{
	  "_id": ObjectId("580961923ec41a29daaf3196"),
	  "name": "Bulbassauro",
	  "description": "Chicote de trepadeira",
	  "type": "grama",
	  "attack": 49,
	  "height": 0.4
	}
	Fetched 2 record(s) in 3ms

	```