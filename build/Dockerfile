ARG OWNER=jupyter
ARG BASE_CONTAINER=$OWNER/base-notebook
FROM $BASE_CONTAINER
ARG DEBIAN_FRONTEND=noninteractive

#LABEL maintainer="Jupyter Project <jupyter@googlegroups.com>"

USER root

# Workaround https://unix.stackexchange.com/questions/2544/how-to-work-around-release-file-expired-problem-on-a-local-mirror
RUN echo "Acquire::Check-Valid-Until \"false\";\nAcquire::Check-Date \"false\";" | cat > /etc/apt/apt.conf.d/10no--check-valid-until
RUN apt-get update --yes
RUN apt-get -y install apt-utils
RUN apt-get -y install libc-dev
RUN apt-get -y install build-essential
RUN pip install -U pip