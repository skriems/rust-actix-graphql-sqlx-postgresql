# rust-actix-graphql-sqlx-postgresql
Using GraphQL with Rust and Apollo Federation

![Image of rusty chain](img/pexels-mike-282004.jpg)

## Walkthrough
This repo and accompanying information was presented at [RustLang Los Angeles February 2021 - see video](https://youtu.be/hMIL12Mj7Pw)

This talk covered:
- Core concepts of GraphQL
- Core concepts of GraphQL federation vs schema stitching
- Rust
- SQLx + PostgreSQL
- async-graphql
- actix
- Apollo Federation with Node.js

## Version
See [Cargo.toml](Cargo.toml) version

## Platforms / Technologies
* [Rust](https://www.rust-lang.org/en-US/)
* [Cargo](https://doc.rust-lang.org/cargo/)
* [Actix](https://actix.rs/)
* [GraphQL](https://graphql.org/)
* [Apollo GraphQL](https://www.apollographql.com/)
* [Node.js](https://nodejs.org/en/)

## Get up and running

There are two ways to intialize the database: using `sqlx` or mounting the
migrations folder into the postgres container on `/docker-entrypoint-initdb`.

### Initializing the DB with initdb scripts

Take a look the docker-compose file and comment in the line where the
migrations folder is mounted as `/docker-entrypoint-initdb` and spin up the
container:

```bash
docker-compose up -d
```

### Initializing the DB with sqlx

```bash
$ cargo install sqlx-cli
```

spin up the postgres container using `docker-compose` and invoke the sqlx:

```bash
$ docker-compose up -d
$ sqlx database create
$ sqlx migrate run
```

### build and run the coder microservice
```bash
$ cd ./svc-coder
$ cargo run
```

### build and run the skill microservice
```bash
$ cd ./svc-skill
$ cargo run
```

### run the apollo gateway

```bash
$ cd ./gateway
$ npm install
$ npm run dev
```
