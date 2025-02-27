<!-- this file is generated via docker-builder, do not edit it directly -->


# What is Docker-mojolicious?

Docker-mojolicious is a minimum components to run [Mojolicious](https://mojolicious.org), a real-time web framework and web development toolkit written in [Perl](https://www.perl.org).

All images, unless explicitly defined, are based on [alpine:3.20](https://hub.docker.com/repository/docker/alpine) and provide installed together with these Perl modules:

* [Mojolicious](https://metacpan.org/pod/Mojolicious) v9.38.

# Supported tags and respective Dockerfile links

* docker-mojolicious: [2.0, latest (main/Dockerfile)](https://github.com/EmilianoBruni/docker-mojolicious/blob/master/main/Dockerfile) (size: **56.2MB**)

* docker-mojolicious: [2.0-minion, minion (minion/Dockerfile)](https://github.com/EmilianoBruni/docker-mojolicious/blob/master/minion/Dockerfile) (size: **60.3MB**) based on [alpine:3.20](https://hub.docker.com/repository/docker/alpine) with these additional Perl modules

  * [Minion](https://metacpan.org/pod/Minion) v10.31.
* docker-mojolicious: [2.0-mysql, mysql (mysql/Dockerfile)](https://github.com/EmilianoBruni/docker-mojolicious/blob/master/mysql/Dockerfile) (size: **89.9MB**) based on [alpine:3.20](https://hub.docker.com/repository/docker/alpine) with these additional Perl modules

  * [DBD::mysql](https://metacpan.org/pod/DBD::mysql) v4.051,
  * [DBIx::Class::Loader](https://metacpan.org/pod/DBIx::Class::Loader) v0.21,
  * [DBIx::Class::Schema::Loader](https://metacpan.org/pod/DBIx::Class::Schema::Loader) v0.07052,
  * [Mojolicious::Plugin::DBIC](https://metacpan.org/pod/Mojolicious::Plugin::DBIC) v0.005.
* docker-mojolicious: [2.0-minion-mongodb, minion-mongodb (minion-mongodb/Dockerfile)](https://github.com/EmilianoBruni/docker-mojolicious/blob/master/minion-mongodb/Dockerfile) (size: **65.4MB**) based on [alpine:3.20](https://hub.docker.com/repository/docker/alpine) with these additional Perl modules

  * [Minion](https://metacpan.org/pod/Minion) v10.31,
  * [Mojolicious::Plugin::Mongodbv2](https://metacpan.org/pod/Mojolicious::Plugin::Mongodbv2) v1.01.
* docker-mojolicious: [2.0-mongodb, mongodb (mongodb/Dockerfile)](https://github.com/EmilianoBruni/docker-mojolicious/blob/master/mongodb/Dockerfile) (size: **61.2MB**) based on [alpine:3.20](https://hub.docker.com/repository/docker/alpine) with these additional Perl modules

  * [Mojolicious::Plugin::Mongodbv2](https://metacpan.org/pod/Mojolicious::Plugin::Mongodbv2) v1.01.

# How to use this image

## Generate an example application.

Go to your code folder, call Mojolicious to create the basic application structure with you as the owner.

    $ docker container run --rm -v "$(pwd):/usr/src/app" ebruni/mojolicious mojo generate app MyApp

Start the application as daemon.

    $ cd my_app
    $ docker container run -d --rm -v "$(pwd):/usr/src/app" -p 3000:3000 ebruni/mojolicious morbo script/my_app

To run the container in the foreground and read the output, omit the `-d` and add `-ti`

    $ docker container run --rm -ti -v "$(pwd):/usr/src/app" -p 3000:3000 ebruni/mojolicious morbo script/my_app

Browse to [localhost:3000](http://localhost:3000) and edit the code in the current folder. If you are on Linux or MacOS, the server will restart whenever you change a file. On Windows this works if you use Docker Desktop with WSL 2.

To switch from development to production an run the application as daemon in the full featured non-blocking web server start it with

    $ docker container run -d --rm -v "$(pwd):/usr/src/app" -p 3000:3000 ebruni/mojolicious script/my_app prefork

# Authors

Emiliano Bruni (EB) <info@ebruni.it>

# Changes

| AUTHOR | DATE | VER. | COMMENTS |
|:---|:---:|:---:|:---|
| EB | 2024-10-29 | 2.0 | Updated to alpine 3.20. Mojolicious to v. 9.38 |
| EB | 2022-07-07 | 1.6 | Add DBIC/mysql client support. Add tini package. |
| EB | 2022-06-07 | 1.5 | Update to Mojolicious v. 9.26 |
| EB | 2022-02-24 | 1.4 | Update to Mojolicious v. 9.22 |
| EB | 2021-09-09 | 1.3 | Add tags for Mojolicious::Plugin::Mongodbv2. |
| EB | 2021-09-09 | 1.2 | Removed Minion::Backend::MongoDB. |
| EB | 2021-09-07 | 1.1 | Update Minion::Backend::MongoDB to latest version. |
| EB | 2021-08-23 | 1.0 | Initial Version. |

# Source

The source of this image on [GitHub](https://github.com/EmilianoBruni/docker-mojolicious).
