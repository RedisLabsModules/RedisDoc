[![GitHub issues](https://img.shields.io/github/release/RedisJSON/RedisDoc.svg)](https://github.com/RedisJSON/RedisDoc/releases/latest)
[![CircleCI](https://circleci.com/gh/RedisJSON/RedisDoc/tree/master.svg?style=svg)](https://circleci.com/gh/RedisJSON/RedisDoc/tree/master)

# RedisJSON

## Usage

    JSON.INDEX ADD <index> <field> <path>
    JSON.INDEX DEL <index> <field>
    JSON.INDEX INFO <index> <field>

    JSON.QGET <index> <query> <path>
    JSON.QSET <index> <query> <path> <json> [NX | XX]
    JSON.QDEL <index> <query> <path>

Return value from JSON.QGET is an array of keys and values:

    key
    json
    key
    json

In a language such as Java this could be represented as a `Map<String, Document>`.
    
A query combining multiple paths:
    
    JSON.QGET mytype "@path1:hello @path2:world" d.name


## Build

```bash
cargo build --release
```

## Run

```
redis-server --loadmodule ./target/release/libredisjson.so
```
