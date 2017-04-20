FROM centos:latest

# RUN apt-get update 
# RUN apt-get -y upgrade

# RUN apt-get -y install curl
# RUN apt-get -y install alien 

RUN yum -y install perl
RUN yum -y install alsa-lib

# RUN curl -o /tmp/wolframscript-1.0-1.x86_64.rpm 'http://re-monitor.wolfram.com:8080/view/Mathematica/view/11.1/view/Installer/view/LINUX/job/A-LINUX64-WolframScript.11.1/lastSuccessfulBuild/artifact/rpmbuild/RPMS/x86_64/wolframscript-1.0-1.x86_64.rpm' 
# RUN rpm --install /tmp/wolframscript-1.0-1.x86_64.rpm

RUN curl -o /tmp/wolfram-engine-11.1.0.5693261-1.internal.x86_64.rpm 'http://re-monitor.wolfram.com:8080/job/Installer.WRIEngine.RPM.cloud-internal/lastSuccessfulBuild/artifact/rpmbuild/RPMS/x86_64/wolfram-engine-11.1.0.5693261-1.internal.x86_64.rpm'
RUN rpm --install /tmp/wolfram-engine-11.1.0.5693261-1.internal.x86_64.rpm

RUN mkdir /usr/share/Mathematica
RUN mkdir /usr/share/Mathematica/Licensing
RUN echo "32f1e9ddb614    6514-53237-29273        3725-4053-759P9T        8648-891-829:8,8,16,16:9:20210130" > "/usr/share/Mathematica/Licensing/mathpass"

CMD ["wolfram"]
