FROM ubuntu:latest

# get the essentials
RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install -y apt-utils
RUN apt-get install -y curl 
RUN apt-get install -y wget
RUN apt-get install -y less
RUN apt-get install -y vim

# install nodejs/npm
RUN curl -sL https://deb.nodesource.com/setup_16.x -o ~/nodesource_setup.sh
RUN sh ~/nodesource_setup.sh
RUN apt-get install -y nodejs

# install python & pip
RUN apt-get install -y software-properties-common
RUN add-apt-repository ppa:deadsnakes/ppa
RUN apt-get install -y python3.9
RUN rm /usr/bin/python3
RUN ln -s /usr/bin/python3.9 /usr/bin/python3
RUN ln -s /usr/bin/python3.9 /usr/bin/python
RUN apt-get install -y python3-pip

# install ruby & gem
RUN apt-get install -y ruby-full

# install java
RUN apt-get install -y default-jre

# install pagerduty-cli
# RUN echo y | sh -c "$(curl -sL https://raw.githubusercontent.com/martindstone/pagerduty-cli/master/install.sh)"
RUN npm install -g pagerduty-cli
ENV API_TOKEN="PLACEHOLDER_TOKEN"
ENTRYPOINT echo ${API_TOKEN} | pd auth:set && /bin/bash