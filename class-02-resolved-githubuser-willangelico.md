# be-mean-modulo-mongodb
Estudando BeMean - Módulo MongoDB

## Aula 2

### Criando Database

```
C:\Program Files\MongoDB\Server\3.2\bin>mongo be-mean-pokemons

```
ou

```
C:\Program Files\MongoDB\Server\3.2\bin>mongo
MongoDB shell version: 3.2.8
connecting to: test
> use be-mean-pokemons
switched to db be-mean-pokemons

```

### Listar Databases

```
> show dbs
be-mean  0.005GB
local    0.000GB

```


### Listar Collections

```
> show collections

```

### Inserir dados


```
> var pokemons = [{"name" : "Bulbossauro", "description" : "Chicote de trepadeira", "type" : "grama", "attack" : 49, height: 0.4},{"name" : "Pikachu", "description" : "Rato elétrico bem fofinho", "type" : "electric", "attack" : 55, "height" : 0.4}, {"name" : "Charmander", "description" : "Esse é o cão chupando manga de fofinho", "type" : "fogo", "attack" : 52,"height" : 0.6}, {"name" : "Squirtle", "description" : "Ejeta água que passarinho não bebe", "type" : "água", "attack" : 48, "height" : 0.5}, {"name" : "Squirtle", "description" : "Ejeta água que passarinho não bebe", "type" : "água", "attack" : 48, "height" : 0.5}, {"name" : "Caterpie", "description" : "Larva lutadora", "type" : "inseto", "attack" : 30, "height" : 0.3,"defense" : 35}]

> pokemons
[
        {
                "name" : "Bulbossauro",
                "description" : "Chicote de trepadeira",
                "type" : "grama",
                "attack" : 49,
                "height" : 0.4
        },
        {
                "name" : "Pikachu",
                "description" : "Rato elétrico bem fofinho",
                "type" : "electric",
                "attack" : 55,
                "height" : 0.4
        },
        {
                "name" : "Charmander",
                "description" : "Esse é o cão chupando manga de fofinho",
                "type" : "fogo",
                "attack" : 52,
                "height" : 0.6
        },
        {
                "name" : "Squirtle",
                "description" : "Ejeta água que passarinho não bebe",
                "type" : "água",
                "attack" : 48,
                "height" : 0.5
        },
        {
                "name" : "Squirtle",
                "description" : "Ejeta água que passarinho não bebe",
                "type" : "água",
                "attack" : 48,
                "height" : 0.5
        },
        {
                "name" : "Caterpie",
                "description" : "Larva lutadora",
                "type" : "inseto",
                "attack" : 30,
                "height" : 0.3,
                "defense" : 35
        }
]

> db.pokemons.insert(pokemons)
BulkWriteResult({
        "writeErrors" : [ ],
        "writeConcernErrors" : [ ],
        "nInserted" : 6,
        "nUpserted" : 0,
        "nMatched" : 0,
        "nModified" : 0,
        "nRemoved" : 0,
        "upserted" : [ ]
})
>

```

### Listar dados

```
> db.pokemons.find()
{ "_id" : ObjectId("57a33c1efbfdce50645d01c8"), "name" : "Bulbossauro", "description" : "Chicote de trepadeira", "type" : "grama", "attack" : 49, "height" : 0.4 }{ "_id" : ObjectId("57a33c1efbfdce50645d01c9"), "name" : "Pikachu", "description" : "Rato elétrico bem fofinho", "type" : "electric", "attack" : 55, "height" :0.4 }{ "_id" : ObjectId("57a33c1efbfdce50645d01ca"), "name" : "Charmander", "description" : "Esse é o cão chupando manga de fofinho", "type" : "fogo", "attack" : 52, "height" : 0.6 } { "_id" : ObjectId("57a33c1efbfdce50645d01cb"), "name" : "Squirtle", "description" : "Ejeta água que passarinho não bebe", "type" : "água", "attack" : 48, "height" : 0.5 }{ "_id" : ObjectId("57a33c1efbfdce50645d01cc"), "name" : "Squirtle", "description" : "Ejeta água que passarinho não bebe", "type" : "água", "attack" : 48, "height" : 0.5 }{ "_id" : ObjectId("57a33c1efbfdce50645d01cd"), "name" : "Caterpie", "description" : "Larva lutadora", "type" : "inseto", "attack" : 30, "height" : 0.3, "defense" : 35 }
>
```


### Buscar e armazenar em variável 
```
> var query = {name:"Pikachu"}

> query

{ "name" : "Pikachu" }

> var poke = db.pokemons.findOne(query)

> poke
{
        "_id" : ObjectId("57a33c1efbfdce50645d01c9"),
        "name" : "Pikachu",
        "description" : "Rato elétrico bem fofinho",
        "type" : "electric",
        "attack" : 55,
        "height" : 0.4
}
>

```

### Editar dado

```
> poke.description

Rato elétrico bem fofinho

> poke.description = "rato elétrico fofinho demais"

rato elétrico fofinho demais

> db.pokemons.save(poke)
WriteResult({ "nMatched" : 1, "nUpserted" : 0, "nModified" : 1 })

> db.pokemons.findOne(query)
{
        "_id" : ObjectId("57a33c1efbfdce50645d01c9"),
        "name" : "Pikachu",
        "description" : "rato elétrico fofinho demais",
        "type" : "electric",
        "attack" : 55,
        "height" : 0.4
}
>

```

