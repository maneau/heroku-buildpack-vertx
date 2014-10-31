# Heroku buildpack: Vert.x

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpack) for [Vert.x](http://vertx.io/) apps. Example application [vertx-sample](https://github.com/mthenw/vertx-sample).

Currently it uses following versions:

* JDK **1.7**
* Vert.x **2.1.4**
* Maven **3.2.3**

## Usage

This buildpack assumes that there are at least two files in repository:

* ```src/main/resources/mod.json``` - used to determine if this is vert.x project
* ```server.js``` - by default file that will be launched (of course this can be overrided by Procfile)

Example of Procfile for vert.x

    web: vertx runzip target/vert-name-mod.zip

Example usage:

    $ ls src/main/resources
    server.js

    $ heroku create --stack cedar --buildpack https://github.com/mthenw/heroku-buildpack-vertx.git

    $ git push heroku master

    -----> Fetching custom git buildpack... done
    -----> Vert.x app detected

    -----> Installing OpenJDK7u2..... done
    -----> Installing Vert.x..... done
    -----> Installing Maven ..... done

    -----> Launching... done

This buildpack is based on [tomaslin/heroku-buildpack-vertx-jdk7](https://github.com/tomaslin/heroku-buildpack-vertx-jdk7).

## License

MIT
