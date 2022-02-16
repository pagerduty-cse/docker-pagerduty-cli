FROM alpine:latest

# get the essentials
RUN apk update && apk upgrade
RUN apk add bash
RUN apk add curl
RUN apk add nodejs
RUN apk add npm

# install pagerduty-cli
RUN npm install -g pagerduty-cli
ENV API_TOKEN="PLACEHOLDER_TOKEN"
ENTRYPOINT echo ${API_TOKEN} | pd auth:set && /bin/bash
