docker pull ubuntu
docker build . -t ubuntu-new
docker run -i -t ubuntu-new /bin/bash