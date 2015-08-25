# Netty-spring example with Mybatis
TCP communication server with Netty, spring-boot, mybatis

This TCP Communication Service is a simple example for developer who want to make tcp service with Spring-Boot, mybatis and Netty.

## Feature
* Telnet Client can send message to other telnet client.
* Telnet Client can retrieve User Information from RDBMS(H2 DB).

## Install
This example uses embedded DBMS(h2 db). So, you don't need to install any DBMS.

## How to use
* Run com.zbum.example.socket.server.netty.Application with IDE or Maven
```
    $ mvn spring-boot:run
```
* Connect to this server by telnet command.
```
    $ telnet localhost 8090
    Trying ::1...
    Connected to localhost.
    Escape character is '^]'.
    Your channel key is /0:0:0:0:0:0:0:1:57220
```
* Your channel key (ID) is /0:0:0:0:0:0:0:1:57220
* Connect to this server by telnet command on annother terminal.
```
    $ telnet localhost 8090
    Trying ::1...
    Connected to localhost.
    Escape character is '^]'.
    Your channel key is /0:0:0:0:0:0:0:1:57221
```
* From now, you can send message to /0:0:0:0:0:0:0:1:57220 channel by below
```
    /0:0:0:0:0:0:0:1:57220::I Love You!!!
```
* Then, you can receive Message like below
```bash
    $ telnet localhost 8090
    Trying ::1...
    Connected to localhost.
    Escape character is '^]'.
    Your channel key is /0:0:0:0:0:0:0:1:57220
    I Love You!!!
```

* Then, you can retrieve user data by command below.
```bash
    $ telnet localhost 8090
    Trying ::1...
    Connected to localhost.
    Escape character is '^]'.
    Your channel key is /0:0:0:0:0:0:0:1:63390
    name?zbum
    010-1111-2222
    name?manty
    010-1111-3333
    name?all
    zbum:010-1111-2222
    manty:010-1111-3333
```