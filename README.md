<!-- this file is generated via docker-builder, do not edit it directly -->


# What is Mojolicious?

Mojolicious has minimum components to run [Mojolicious](https://mojolicious.org), a real-time web framework and web development toolkit written in [Perl](https://www.perl.org).

All images are based on alpine:3.14 and provide installed together with these Perl modules:

* [Mojolicious](https://metacpan.org/pod/Mojolicious) v9.21.

# Supported tags and respective Dockerfile links

* Mojolicious: [1.2, latest (main/Dockerfile)](https://github.com/EmilianoBruni/docker-mojolicious/blob/master/main/Dockerfile) (size: **48MB**)

* Mojolicious: [1.2-minion, minion (minion/Dockerfile)](https://github.com/EmilianoBruni/docker-mojolicious/blob/master/minion/Dockerfile) (size: **52MB**) with these additional Perl modules

	* [Minion](https://metacpan.org/pod/Minion) v10.22.

# How to use this image

## Example application

Go to your code folder, call Mojolicious to create the basic application
structure with you as the owner.

    $ docker container run --rm -v "$(pwd):/usr/src/app" ebruni/mojolicious mojo generate app MyApp

Start the application as daemon.

    $ cd my_app
    $ docker container run -d --rm -v "$(pwd):/usr/src/app" -p 3000:3000 ebruni/mojolicious morbo script/my_app

To run the container in the foreground and read the output, omit the `-d` and add `-ti`

    $ docker container run --rm -ti -v "$(pwd):/usr/src/app" -p 3000:3000 ebruni/mojolicious morbo script/my_app

Browse to [localhost:3000](http://localhost:3000) and edit the code in the
current folder. If you are on Linux or MacOS, the server will restart whenever
you change a file. On Windows this works if you use Docker Desktop with WSL 2.

To switch from development to production an run the application as daemon in
the full featured non-blocking web server start it with

    $ docker container run -d --rm -v "$(pwd):/usr/src/app" -p 3000:3000 ebruni/mojolicious script/my_app prefork

# Source

The source of this image on [GitHub](https://github.com/EmilianoBruni/docker-mojolicious).
