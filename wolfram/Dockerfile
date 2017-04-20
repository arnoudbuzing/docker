FROM centos:latest

# for the wolfram-engine rpm itself

RUN yum -y install perl
RUN yum -y install alsa-lib

# for the frontend

RUN yum -y groupinstall X11

# wolfram-engine

RUN rpm --install 'http://re-monitor.wolfram.com:8080/job/Installer.WRIEngine.RPM.cloud-internal/lastSuccessfulBuild/artifact/rpmbuild/RPMS/x86_64/wolfram-engine-11.1.0.5693261-1.internal.x86_64.rpm'

# password stuff

RUN mkdir /usr/share/Mathematica
RUN mkdir /usr/share/Mathematica/Licensing
# RUN echo "32f1e9ddb614 6514-53237-29273 3725-4053-759P9T 8648-891-829:8,8,16,16:9:20210130" > "/usr/share/Mathematica/Licensing/mathpass"
RUN echo "!mathlm.wolfram.com" > "/usr/share/Mathematica/Licensing/mathpass"

# define user

RUN useradd -ms /bin/bash wolfram
USER wolfram
WORKDIR /home/wolfram

# switch "bash" to "wolfram" when everything works

CMD ["wolfram"]
