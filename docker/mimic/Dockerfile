## Mimic

FROM ubuntu:14.04
MAINTAINER Chris Powell <chris.powell@rackspace.com>

RUN apt-get -qq update && apt-get -qq upgrade && apt-get install -qqy \                                  
    curl \ 
    python-dev \                                                                                         
    git \
    libev4 \
    libev-dev \
    libffi-dev \                                                                                         
    libssl-dev \
    python-pip \                                                                                         
    python-setuptools 
    
# Get a working version of pip for ubuntu 14.04:
# https://bugs.debian.org/cgi-bin/bugreport.cgi?bug=744145
RUN /usr/bin/curl -s https://bootstrap.pypa.io/get-pip.py | python

WORKDIR /home/source
RUN git clone https://github.com/rackerlabs/mimic .
RUN pip install -e .

EXPOSE 8900
CMD ["twistd", "-n", "mimic"]
