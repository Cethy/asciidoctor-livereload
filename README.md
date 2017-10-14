Asciidoctor-livereload
===

Ready-to-go docker environment for Asciidoctor livereload.

## Requirements
In the current implementation, you will need the [livereload extension](http://livereload.com/extensions/) for your web navigator.

And docker, obviously.


## How to use
- Put your `asc` files into `/book` (or edit the volumes in `docker-compose.yml` file).
- Build and launch docker-compose :


    docker-compose build
    docker-composer up

- Modify an `asc` file (to kickoff the ascidoctor watcher) ;
- Open `ouput/index.html` into your favorite navigator ;
- Active the livereload extension ;

That's it !


## What's under the hood ?

### [`cethy/alpine-asciidoctor-watcher:micro`](https://github.com/Cethy/alpine-asciidoctor-watcher/)
Docker image (20Mo) which watch for modification into the `/book` directory and run asciidoctor when modified.

### [`franckdelage/docker-livereload`](https://github.com/franckdelage/docker-livereload)
Docker image (16Mo) which watch for modification into the `/output` directory and reload the page in the navigator.


## Related work
- Asciidoctor Builder docker image [cethy/alpine-asciidoctor-builder](https://github.com/Cethy/alpine-asciidoctor-builder)
 ([on docker hub](https://hub.docker.com/r/cethy/alpine-asciidoctor-builder/))
- Asciidoctor Watcher docker image [cethy/alpine-asciidoctor-watcher](https://github.com/Cethy/alpine-asciidoctor-watcher)
 ([on docker hub](https://hub.docker.com/r/cethy/alpine-asciidoctor-watcher/))


## Todo
- Use the right livereload image (currently using a fork)
- Remove the livereload extension requirement (add a nginx proxy w/ js injection ?)
