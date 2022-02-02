FROM ubuntu:20.04

# get the essentials
RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install curl -y
RUN apt-get install wget -y
RUN apt-get install less -y
RUN apt-get install vim -y

# install python & pip
RUN apt-get install software-properties-common -y
RUN add-apt-repository ppa:deadsnakes/ppa
RUN apt-get install python3.9 -y
RUN rm /usr/bin/python3
RUN ln -s /usr/bin/python3.9 /usr/bin/python3
RUN ln -s /usr/bin/python3.9 /usr/bin/python
RUN apt-get install python3-pip -y

# install ruby & gem
RUN apt-get install ruby-full -y

# install java
RUN apt-get install default-jre -y

# install pagerduty-cli
RUN echo y | sh -c "$(curl -sL https://raw.githubusercontent.com/martindstone/pagerduty-cli/master/install.sh)"
ENV API_TOKEN="PLACEHOLDER_TOKEN"
ENTRYPOINT echo ${API_TOKEN} | pd auth:set && /bin/bash