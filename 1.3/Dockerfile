FROM ubuntu
RUN set -x && \
    apt-get update && \
    apt-get install build-essential patch wget -y
WORKDIR /tmp

RUN wget https://legacy.python.org/download/releases/src/python-1.3.tar.gz
RUN tar -xf python-1.3.tar.gz
WORKDIR /tmp/Python-1.3

COPY diff.patch diff.patch
RUN patch -p0 < diff.patch
RUN ./configure
RUN make install
RUN make libinstall
WORKDIR /

CMD python
