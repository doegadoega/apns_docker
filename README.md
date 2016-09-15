# Apns push server with Docker

## Usage

### Create docker image

```bash
git clone git@github.com:fromkk/apns_docker.git
cd ./apns_docker
docker build -t apns:ubuntu .
```

### Set up your information

modify **share/apns/apns.sh**

```bash
# iOS device token
token="YOUR TOKEN HERE"
# full path .pem file
pemfile="PEM FILE PATH HERE"
# iOS apps bundle identifier
bundleIdentifier="BUNDLE IDENTIFIER HERE"
# push content
pushData='{"aps": {"alert": "Push Test", "sound": "default", "badge": 3}}'
```

### Run docker

```bash
docker run -it -v `pwd`/share/apns:/apns apns:ubuntu /bin/bash
sh /apns/apns.sh
```
