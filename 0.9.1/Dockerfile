FROM ubuntu
RUN set -x && \
    apt-get update && \
    apt-get install build-essential patch wget -y
WORKDIR /tmp

COPY python-0.9.1/ python-0.9.1/

WORKDIR /tmp/python-0.9.1/src/
RUN make
RUN cp python /usr/bin
WORKDIR /

CMD python
