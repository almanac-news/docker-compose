# docker-compose

## Production Version

This docker-compose file can be run from any location to boot up an environment from our latest production builds.

**Don't forget to install the Redis data-volume container before running this.** The Redis data-volume is installed by running the following: $ docker create -v /data --name cachedb redis /bin/true

This will allow Redis' data to persist after containers are shut down. The *cachedb* container will remain deactivated in the background to store this data. Don't delete it without the '-v' flag, or the volume will be left dangling and take up disk space.
