# be-mean-modulo-mongodb
Estudando BeMean - Módulo MongoDB

## Importando os restaurantes

```
C:\Program Files\MongoDB\Server\3.2\bin> mongoimport --db be-mean --collection restaurantes --drop --file c:/beMean/restaurantes.json
2016-08-01T11:59:37.038-0300    connected to: localhost
2016-08-01T11:59:37.050-0300    dropping: be-mean.restaurantes
2016-08-01T11:59:39.047-0300    imported 25359 documents
```

## Contanto os restaurantes

```
C:\Program Files\MongoDB\Server\3.2\bin>mongo be-mean
MongoDB shell version: 3.2.8
connecting to: be-mean
> db.restaurantes.find({}).count()
25359
```
