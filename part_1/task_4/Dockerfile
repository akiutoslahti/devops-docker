FROM ubuntu:latest
WORKDIR /app
COPY curl.sh .
RUN apt-get update && apt-get upgrade -y && apt-get install -y curl
CMD ./curl.sh
