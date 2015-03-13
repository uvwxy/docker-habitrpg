# HabitRPG - Docker Container

## Building

```
docker build -t uvwxy/habitrpg .
```

## Setup MongoDB

First, run a MongoDB instance in the background:

```
docker run --name habitrpg-mongo -d mongo
```

## Run HabitRPG

Important keep the linkname consistent with the name of the MongoDB container above. Also the alias `db`is used in the `config.json` as the hostname.

Start the HabitRPG container and link it with the MongoDB node `habitrpg-mongo`.

```
docker run --name habitrpg --link habitrpg-mongo:db -p 3000:3000 -d uvwxy/habitrpg
```

