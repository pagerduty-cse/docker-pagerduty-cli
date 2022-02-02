FROM alpine:3.14.0

# get the essentials
RUN apk update && apk upgrade
RUN apk add bash
RUN apk add curl
RUN apk add nodejs

# install pagerduty-cli
RUN echo y | sh -c "$(curl -sL https://raw.githubusercontent.com/martindstone/pagerduty-cli/master/install.sh)"
ENV API_TOKEN="PLACEHOLDER_TOKEN"
ENTRYPOINT echo ${API_TOKEN} | pd auth:set && /bin/bash
