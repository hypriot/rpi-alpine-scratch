# rpi-alpine-scratch

[![dockeri.co](http://dockeri.co/image/hypriot/rpi-alpine-scratch)](https://registry.hub.docker.com/u/hypriot/rpi-alpine-scratch/)

Raspberry Pi compatible Docker Image with a minimal `linux` system.

## Details
- [Source Project Page](https://github.com/hypriot)
- [Source Repository](https://github.com/hypriot/rpi-alpine-scratch)

## usage as base for a minimal linux server

first create the Dockerfile

```bash
cat << EOM >> Dockerfile
FROM hypriot/rpi-alpine-scratch

RUN apk update && \
apk upgrade && \
apk add bash && \
rm -rf /var/cache/apk/*

CMD ["/bin/bash"]
EOM
```

Now you can build a minimalistic system with:

```bash
docker build -t alpine-mini .
```


## How to create this image

Run all the commands from within the project root directory.

### Build the Docker Image
```bash
make create
```

#### Push the Docker Image to the Docker Hub
* First use a `docker login` with username, password and email address
* Second push the Docker Image to the official Docker Hub

```bash
make push
```

## License

The MIT License (MIT)

Copyright (c) 2015 Hypriot

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
