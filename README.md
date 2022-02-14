# Visual Regression
### Overview

A Dockerized Cypress Image with an integrated light-weight desktop environment. 

### Usage Simple
**Docker Compose GUI:**
```
docker-compose up
```

**Docker Compose Headless:**
```
docker-compose -f docker-compose-headless.yml up
```
### Usage Advanced
**Linux Command examples GUI (Developer mode in web browser):** 

```
docker run --rm -p 6901:6901 -p 5901:5901 -v $PWD/cypress:/src/cypress chronos86/visual-regression:1.0.0 --name at
```

**Linux Command examples NON GUI (Command line only - one time headless testing):**
```
docker run --rm -v $PWD/cypress:/src/cypress -it --name at --entrypoint /src/entrypoint2.sh chronos86/visual-regression:1.0.0
```

**Linux Command examples NON GUI (Command line only - headless testing +  bash):**
```
docker run -d --rm -v $PWD/cypress:/src/cypress -it --name at --entrypoint /src/entrypoint.sh chronos86/visual-regression:1.0.0
docker exec --workdir /src -it at cypress run --headless --browser firefox
```

**Windows:**

```
Use ${PWD} in Powershell
```

You will be able to access the noVNC windows at [http://localhost:6901](http://localhost:6901) or use your VNC viewer with `localhost:5901`

#### Ports

**6901** is exposed by default for the noVNC.

**5901** is exposed by default for VNC.

### Sudo password
The default username in the container is docker and you can use `sudo` without the need of a password.

### DockerHub

DockerHub link of the images:

- https://hub.docker.com/repository/docker/chronos86/visual-regression

## Image Contents

- [Xvfb](http://www.x.org/releases/X11R7.6/doc/man/man1/Xvfb.1.xhtml) - X11 in a virtual framebuffer
- [TigerVNC](https://github.com/TigerVNC/tigervnc) - A VNC server that scrapes the above X11 server
- [noNVC](https://github.com/novnc/noVNC) - A HTML5 canvas vnc viewer
- [xfce4](https://www.xfce.org/) - a small desktop environment
- [Cypress](https://github.com/cypress-io/cypress)-  Testing tool

## Maintainers

Grzegorz Kudliński [Github](https://github.com/gkudlinski)
