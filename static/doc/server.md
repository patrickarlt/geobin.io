# Geobin Server

The Geobin server hosts the Geobin [web client] as well as the [API]. It is written in [go] and uses [redis] so, assuming you have a working go [dev environment] and [redis server] running the following should get you up and running.

## Setup

```bash
> go get github.com/esripdx/geobin.io
> cd $GOPATH/src/github.com/esripdx/geobin.io
> make setup # (runs `go get -t` and `npm install`)
> cp config.json.dist config.json
```

## Configure

Geobin comes with a default `config.json` file which should get you up and running for development, you'll just need to copy `config.json.dist` to `config.json` (as listed in the Setup steps above).

### Config Keys

* `Host` The http host to listen on

  ```javascript
  "Host": "localhost"
  ```

* `Port` The http port to listen on

  ```javascript
  "Port": 8080
  ```

* `RedisHost` The redis host (with port)

  ```javascript
  "RedisHost": "127.0.0.1:6379"
  ```

* `RedisPass` The redis password

  ```javascript
  "RedisPass": ""
  ```

* `RedisDB` The redis db to connect to

  ```javascript
  "RedisDB": 0
  ```

* `NameVals` The set of valid characters to be used in the randomly generated binIDs.

  ```javascript
  "NameVals": "023456789abcdefghjkmnopqrstuvwxyzABCDEFGHJKMNOPQRSTUVWXYZ"
  ```

* `NameLength` The number of chars to be used in each binID.

  ```javascript
  "NameLength": 10
  ```

## Run

```bash
> make run
```

## Test

```bash
> go test
```

## Build

```bash
> go build -o geobin
```

[go]: http://golang.org
[dev environment]: http://golang.org/doc/install
[redis]: http://redis.io
[redis server]: http://redis.io/download
[web client]: client.md
[API]: api.md
