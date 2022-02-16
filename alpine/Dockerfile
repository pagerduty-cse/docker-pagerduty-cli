FROM alpine:latest

# get the essentials
RUN apk update && apk upgrade
RUN apk add bash
RUN apk add curl
RUN apk add nodejs
RUN apk add npm

# install pagerduty-cli
RUN npm install -g pagerduty-cli
ENTRYPOINT /bin/bash