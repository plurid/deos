To have

- OS Entities
- OS Instances

The OS Entities are user configured, the OS Instances are automatically created at runtime, without the user noticing them.

The OS Entity configuration file will spawn a MacOS Entity with Adobe Photoshop installed, authenticated, and opened


``` yaml
os: macos:10.15.3 # or window:10 # or ubuntu:18.04 # or etc

name: macos # given name

apps:
  adobe/photoshop:
    version: 2019
    open: true
    login:
      - username: SECRET_1
      - password: SECRET_2

secrets:
  SECRET_1: ''
  SECRET_2: ''
```



Architecture

On a cluster of computers setup the deos servers. A user should be able to log into the deos server through a client (web, native), have access to a file system, load OSes into plurid planes, install/setup applications, setup OS configurations.


The deos servers consists of:
+ a web gateway server, receiving requsts, streaming the data, controlling user authentication, etc.
+ a virtualizer internal server, responsible for running the OS images with their applications and sending the pixels stream to the web server
+ an internal file server, where all the user data is stored, or where the user data is cached into, if using local main storage
