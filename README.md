# docker-compose

##Development Version

This docker-compose file is used for **active development** on a Docker container.

It will map volumes to the source directories of the Web Server and App Service containers. This requires a specific directory setup at the location of the `docker-compose.yml` file. In order for the volumes to map correctly, this file must exist in a single directory which also contains both the entire **almanac-app-service** and **almanac-web** repos.

In order for the containers to function properly with volumes, the sub-directories must have all dependencies installed. For example, this means that `npm install` must be run in the web directory.

To remove volume mapping, delete the '*volume*' sections of the `yml` file.

**Don't forget to install the Redis data-volume container before running this.**

The Redis data-volume is installed by running the following: 
`$ docker create -v /data --name cachedb redis /bin/true`

This will allow Redis' data to persist after containers are shut down. The '*cachedb*' container will remain deactivated in the background to store this data. Don't delete it without the `-v` flag, or the volume will be left dangling and take up disk space.
