# Licode

An Open Source WebRTC Communications Platform.

With Licode you can host your own WebRTC conference provider and build applications on top of it with easy to use APIs: [client-side](http://licode.readthedocs.io/en/master/client_api/) and [server-side](http://licode.readthedocs.io/en/master/server_api/).

You have two options to start using Licode:

* If you want a quick taste of what Licode can do or you are familiar with [Docker](http://www.docker.com) - [How to use the docker image or build your own](http://licode.readthedocs.io/en/master/docker/)

* If you are interested in contributing, want to get a better view of the Licode architecture or you don't trust those fancy containers - [How to build Licode from source](http://licode.readthedocs.io/en/master/from_source/)


More info at:
http://www.lynckia.com/licode

## Build your own image and run the container from it

You have to git clone Licode's code from GitHub and navigate to docker directory. There, to compile your own image just run:
```
sudo docker build -t licode-image .
```
This builds a new Docker image following the steps in Dockerfile and saves it in your local Docker repository with the name licode-image. You can check the available images in your local repository using:
```
sudo docker images
```
Now you can run a new container from the image you have just created with:
```
MIN_PORT=30000; MAX_PORT=30050; sudo docker container run --rm --name licode -v /home/conneczodev/extras:/home/conneczodev/extras -p  3000:3000 -p $MIN_PORT-$MAX_PORT:$MIN_PORT-$MAX_PORT/udp -p 3001:3001  -p 8080:8080 -e "MIN_PORT=$MIN_PORT" -e "MAX_PORT=$MAX_PORT" -e "PUBLIC_IP=128.199.74.227" licode-image
```

## License

The MIT License

Copyright (C) 2012 Universidad Politecnica de Madrid.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
