## 1. By default, Docker runs containers as root
* Running a process as root in a Docker container gives the process full privileges within the container, but not on the host system.

```
docker run -it ubuntu bash
whoami
```

## 2. Run as non-root

Dockerfile
```
FROM ubuntu
RUN useradd -m demo01
USER demo01
```

Build and run
```
docker build -t myimage .
docker run -it myimage bash
whoami
```

## 3. Running in Privileged Mode
* Full access to the host system (security risk)
* You can access to all devices on the host.
```
docker run --privileged -it ubuntu bash
```