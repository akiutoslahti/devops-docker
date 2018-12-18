FROM ubuntu:latest

WORKDIR /app
EXPOSE 8080

RUN apt-get update && apt-get upgrade -y && apt-get install -y wget default-jdk
RUN wget https://github.com/akiutoslahti/ohtu-miniprojekti2018/releases/download/sprint4/ohtutips-sprint4.jar
CMD java -jar ohtutips-sprint4.jar
