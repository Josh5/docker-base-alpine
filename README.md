
# josh5/base-alpine

### Based upon [Alpine Linux](https://hub.docker.com/_/alpine/) and [S6 overlay](https://github.com/just-containers/s6-overlay), this serves as a base template container for all other docker containers created by Josh.5.

![alpine](https://alpinelinux.org/alpinelinux-logo.svg)

## Features:
|  |  |
| --- | --- |
| Base:  | Alpine Linux  |
| Init:  | s6 overlay  |
| Additinal services:  | ca-certificates  |
|   | curl  |
|   | coreutils  |
|   | nano  |
|   | shadow  |
|   | tar  |
|   | tzdata  |
|   | unzip  |


## Configuration:

Configuration is stored in /config/
User's app binaries can be installed to /app
* Default user "docker"
* Hosts file configurable in /config/hosts
* SSH access to root with password 'root'

Additional params to your container:
* `-e PGID` for setting the GroupID of the default user
* `-e PUID` for setting the UserID of the default user
* `-e TZ` for setting timezone information, eg Europe/London


## NOTES:
It is strongly recommended that you change the default root password for ssh login if you intened to use it in production.
Change the password with 'echo 
```bash
"root:something_else" | chpasswd'
```
or to disable root access in ssh login all together:
```bash
sed -i s/#PermitRootLogin.*/PermitRootLogin\ no/ /etc/ssh/sshd_config
```