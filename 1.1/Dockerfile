FROM ubuntu
RUN set -x && \
    apt-get update && \
    apt-get install build-essential patch wget -y
WORKDIR /tmp

RUN wget https://legacy.python.org/download/releases/src/python1.1.tar.gz
RUN tar -xf python1.1.tar.gz
WORKDIR /tmp/python-1.1

COPY diff.patch diff.patch
RUN patch -p0 < diff.patch
RUN ./configure
RUN make install
# Currently segfaults, see https://github.com/di/vintage-python/issues/1
#RUN make libinstall
WORKDIR /

CMD python
