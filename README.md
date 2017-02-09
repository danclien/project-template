# project-template

These `bash` scripts start up a Docker-based development environment and runs
commands in the container. The scripts default to using `Dockerfile.dev`
in the root of the project directory as the `Dockerfile`.

The scripts also:

* Mounts the project directory as `/app` inside the container
* Port forwards `ssh-agent` into the container

**Note:** This has only been tested on Linux.


## Usage

* Run `bin/docker-bash` to open an interactive `bash` session.
* Run `bin/docker-run` and pass in a command to run that command.


## Notes

### `bin/_bootstrap`

Create the Docker image and sets up environment variables for the other
scripts. The image is tagged with the the name of the project directory.

**Note:** The scripts will break if the project directory is not a valid
Docker tag name.

### `bin/docker-bash`

Starts up an interactive `bash` session in the container. The container will be
deleted after it's complete.

### `bin/docker-run`

Pass in a command to run. The container will be deleted after it's complete.
