FROM centos:latest

# for the wolfram-engine rpm itself

RUN yum -y install perl
RUN yum -y install alsa-lib

# for the frontend

RUN yum -y groupinstall X11

# wolfram-engine

RUN rpm --install wolfram-engine-11.1.0.5693261-1.internal.x86_64.rpm

# password stuff

RUN mkdir /usr/share/Mathematica
RUN mkdir /usr/share/Mathematica/Licensing
RUN echo "!mathlm.wolfram.com" > "/usr/share/Mathematica/Licensing/mathpass"

# define user

RUN useradd -ms /bin/bash wolfram
USER wolfram
WORKDIR /home/wolfram

# switch "bash" to "wolfram" when everything works

CMD ["wolfram"]
