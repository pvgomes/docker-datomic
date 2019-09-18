# Docker Datomic

[![Docker Pulls](https://img.shields.io/docker/pulls/akiel/datomic-free.svg)](https://hub.docker.com/r/pvgomes/datomic/)


## Setup

To start a container with Docker

    docker run -d -e ADMIN_PASSWORD="admin" -e DATOMIC_PASSWORD="datomic" -p 4334-4336:4334-4336 --name datomic-free pvgomes/datomic

You can access your databases through this URIs

    datomic:free://localhost:4334/<DB_NAME>?password=datomic


## Usage examples
deps.edn
```
{:deps
 {org.clojure/data.csv {:mvn/version "0.1.4"}
  org.clojure/data.json {:mvn/version "0.2.6"}
  org.clojure/data.generators {:mvn/version "0.1.2"}
  org.clojure/clojure {:mvn/version "1.10.1"}
  com.datomic/datomic-free {:mvn/version "0.9.5697"}}
 :paths ["src"]}
```

### Clojure connect to datomic example
src/example.clj
```clojure
;; create
(require '[datomic.api :as d])
(def db-uri "datomic:free://localhost:4334/databasename?password=datomic")
(d/create-database db-uri)

;; connect to database
(def conn (d/connect db-uri))
```