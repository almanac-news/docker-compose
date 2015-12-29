# docker-compose

##Development Version

This docker-compose file is used for development on a Docker container **without volumes or hot-module reloading**. For volumes and hot-reloading, see the docker-compose.yml files within specific repos.

When adding environment variables to the python app service, do **not** use quotes.

In order for the containers to function properly with volumes, the sub-directories must have all dependencies installed. For example, this means that `npm install` must be run in the web directory.

**Don't forget to install the Redis and RethinkDB data-volume containers before running this.**

The Redis data-volume is installed by running the following: 
`$ docker create -v /data --name cachedb redis /bin/true`

The RethinkDB data-volume is installed by running the following: 
`$ docker create -v /data --name rtdb rethinkdb /bin/true`

**The RethinkDB admin console is available on Port 8080.**

This will allow Redis' data to persist after containers are shut down. The '*cachedb*' container will remain deactivated in the background to store this data. Don't delete it without the `-v` flag, or the volume will be left dangling and take up disk space.
