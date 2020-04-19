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
