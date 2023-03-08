# Quick reference

-	**Maintained by**:  
	[Matt Linebarger](https://github.com/mattlinebarger), Sr. Manager, Customer Success Engineering @ [PagerDuty](https://www.pagerduty.com/)

-	**Where to get help**:  
	For help with the Docker images please contact Matt at <mlinebarger@pagerduty.com>. For help with PagerDuty CLI please check out the [PagerDuty CLI User Guide](https://github.com/martindstone/pagerduty-cli/wiki/PagerDuty-CLI-User-Guide).

-	**Where to file issues**:  
	Issues can be filed on [GitHub](https://github.com/pagerduty-cse/docker-pagerduty-cli/issues)

-	**Source of this description**:  
	[GitHub repo's README](https://github.com/pagerduty-cse/docker-pagerduty-cli/blob/main/README.md)

# Supported tags and respective `Dockerfile` links

-   [`alpine`, `alpine-lite`, `lite`, `latest`](https://github.com/pagerduty-cse/docker-pagerduty-cli/blob/main/alpine/Dockerfile)
-   [`ubuntu`, `full`, `ubuntu-full`](https://github.com/pagerduty-cse/docker-pagerduty-cli/blob/main/ubuntu/Dockerfile)

# What is pagerduty-cli?

Containerized versions of [Martin Stone's](https://github.com/martindstone) [command-line interface for PagerDuty](https://github.com/martindstone/pagerduty-cli). PagerDuty CLI uses the PagerDuty REST API to communicate with PagerDuty. It’s implemented in TypeScript and Node.js, using the wonderful [oclif](https://oclif.io/) library.

The [Alpine](https://github.com/pagerduty-cse/docker-pagerduty-cli/blob/main/alpine/Dockerfile) image is based on the [latest Alpine](https://hub.docker.com/_/alpine) image with bare essentials needed to run PagerDuty CLI.

The [Ubuntu](https://github.com/PagerDuty/docker-pagerduty-cli/blob/main/ubuntu/Dockerfile) image is based on the [latest Ubuntu](https://hub.docker.com/_/ubuntu) image with the following tools installed: curl, wget, less, vim, python3, go, pip, ruby, gem, java, nodejs & npm. These additional tools are included for use in the [docker-pd-runner](https://github.com/PagerDuty/docker-pd-runner) application, which creates a containerized PD Runner for [PagerDuty Rundeck Actions](https://support.pagerduty.com/docs/rundeck-actions).

# How to use this image

## Usage

Starting a PagerDuty CLI container is simple (this example is using the Alpine 'latest' tag):
```
$ docker run -dit --name my-pagerduty-cli pagerdutycs/pagerduty-cli:latest
```

To log into a bash shell of your container:
```
$ docker exec -it my-pagerduty-cli /bin/bash
```

Add an authenticated PagerDuty domain (add your PagerDuty API key when prompted):
```
$ docker exec -it my-pagerduty-cli pd auth:set
```

To run PagerDuty CLI commands from the host (this example lists closed incidents):
```
$ docker exec -it my-pagerduty-cli pd incident:list -s=closed
```
