# Docker Exec Image: Clojure

A Dockerfile describing an container capable of executing Clojure source files.

# Build

```sh
git clone https://github.com/docker-exec/clojure.git
docker build -t dexec/clojure .
```

# Usage

In a directory containing a script e.g. foo.clj, run:

```sh
docker run -t --rm \
    -v $(pwd -P)/foo.clj:/tmp/dexec/build/foo.clj \
    dexec/clojure foo.clj
```

## Passing arguments to the script

Arguments can be passed to the script using any of the following forms:

```
-a argument
--arg argument
--arg=argument
```

Each argument passed must be prefixed in this way, e.g.

```sh
docker run -t --rm \
    -v $(pwd -P)/foo.clj:/tmp/dexec/build/foo.clj \
    dexec/clojure foo.clj \
    --arg='hello world' \
    --arg=foo \
    --arg=bar
```
