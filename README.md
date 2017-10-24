Asciidoctor-livereload
===

Ready-to-go docker environment for Asciidoctor livereload.

## How to use
- Put your `asc` files into `/book` (or edit the volumes in `docker-compose.yml` file).
- Build and launch docker-compose :


    docker-compose build
    docker-compose up

- Modify an `asc` file (to kickoff the ascidoctor watcher) ;

- open your browser at [http://localhost:8941](http://localhost:8941) ;

- modify a file in your watched directory ;

- Magic, the page is refreshed ! :o


## What's under the hood ?

### [`cethy/alpine-asciidoctor-watcher:micro`](https://github.com/Cethy/alpine-asciidoctor-watcher/)
Docker image (20Mo) which watch for modification into the `/book` directory and run asciidoctor when modified.

### [`cethy/apline-nginx-livereload-injection:v1.0`](https://github.com/Cethy/apline-nginx-livereload-injection/)
Docker image (7Mo) which act as a reverse proxy for `/output` and inject the livereload js snippet.

### [`cethy/alpine-livereload`](https://github.com/Cethy/alpine-livereload)
Docker image (16Mo) which watch for modification into the `/output` directory and reload the page in the navigator.


## Related work
- Asciidoctor Builder docker image [cethy/alpine-asciidoctor-builder](https://github.com/Cethy/alpine-asciidoctor-builder)
 ([on docker hub](https://hub.docker.com/r/cethy/alpine-asciidoctor-builder/))
- Asciidoctor Watcher docker image [cethy/alpine-asciidoctor-watcher](https://github.com/Cethy/alpine-asciidoctor-watcher)
 ([on docker hub](https://hub.docker.com/r/cethy/alpine-asciidoctor-watcher/))


## Changelog
### v2.0
- `cethy/apline-nginx-livereload-injection` added to remove dependency on the livereload extension.

### v1.0
- require [livereload extension](http://livereload.com/extensions/) for your web browser to work.
