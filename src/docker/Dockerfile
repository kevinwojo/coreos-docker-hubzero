############################################################
# Dockerfile to build HUBzero container images
# Based on Centos 7
############################################################

# Set the base image to Ubuntu
FROM centos:7

# File Author / Maintainer
MAINTAINER Kevin Wojkovich <kevinw@purdue.edu>

################## BEGIN INSTALLATION ######################

# Install wget
RUN yum install wget -y

# SELinux already disabled

# Add HUBzero RPM repository
ADD hubzero.repo /etc/yum.repos.d/

# Add the EPEL repository
RUN yum install epel-release -y

# Add the openVZ repo
RUN wget -P /etc/yum.repos.d/ http://ftp.openvz.org/openvz.repo

# Add the repo keys
RUN rpm --import http://packages.hubzero.org/rpm/hubzero-rpm-key-pub


# Run the system updates
RUN yum update -y


##################### INSTALLATION END #####################

# Expose the default port
EXPOSE 80
EXPOSE 443
EXPOSE 22
EXPOSE 25

# Default port to execute the entrypoint (MongoDB)
#CMD ["--port 27017"]

# Set default container command
#ENTRYPOINT usr/bin/mongod
