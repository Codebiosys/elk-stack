# ELK Stack Reference

This project serves as a reference implementation of an ELK stack within
a Docker environment. Each directory is intended to be installed as it's own container in your project's Docker stack.

## Getting Started

### As a standalone playground

1. Clone the application:

    ```
    > git clone https://github.com/CodeBiosys/elk-stack
    > cd elk-stack
    ```

1. Provision a new Docker machine called `elk-stack`:

    ```
    > docker-machine create -d virtualbox elk-stack
    > eval $(docker-machine env elk-stack)
    > docker-machine ls
	  NAME          ACTIVE   DRIVER       STATE     URL                         SWARM   DOCKER        ERRORS
    elk-stack                 -        virtualbox   Running   tcp://192.168.99.105:2376           v18.06.1-ce
    ```

    **Note the asterisk in the "ACTIVE" column.**


1. Build the application stack and start the services:

    ```
    # Build local services
    > docker-compose build

    # Start up services in Daemon mode
    > docker-compose up -d

    # Follow logs
    > docker-compose logs -f
    ```

    **Note that if you update your permissions YAML file, you need to re-run
    rebuild_permissions**

1. Get the IP address of the machine and use it to navigate to it on your browser:

    ```
    > docker-machine ip elk-stack
    ```


### As an imported service within your stack

You can also install each service via Github link instead of a local directory. To do so, use the `docker-compose.yml` as a reference and replace each build directory with the GitHub link, for example:

```yml

services:

  elasticsearch:
    build: https://YOURGITKEY:@github.com/Codebiosys/elk-stack.git.git#master:elasticsearch
    ...

  logspout:
    build: https://YOURGITKEY:@github.com/Codebiosys/elk-stack.git.git#master:logspout
    ...

  logstash:
    build: https://YOURGITKEY:@github.com/Codebiosys/elk-stack.git.git#master:logstash
    ...

  kibana:
    build: https://YOURGITKEY:@github.com/Codebiosys/elk-stack.git.git#master:kibana
    ...

```

---

## Resources

This project was inspired by the following resources

* https://github.com/deviantony/docker-elk
