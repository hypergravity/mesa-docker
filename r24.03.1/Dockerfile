FROM ubuntu:22.04

# use bash
RUN rm /bin/sh && ln -s /bin/bash /bin/sh

# install dependencies
RUN apt-get update --fix-missing && \
    apt-get install -y bzip2 binutils make perl libx11-6 libx11-dev zlib1g zlib1g-dev tcsh libc6-dev && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

# add user mesa & mkdir mesa
RUN useradd -ms /bin/bash -u 1000 mesa
RUN mkdir -p /mesa && \
    mkdir -p /mesa/work && \
    chown -R mesa:mesa /mesa

USER mesa
# copy code
COPY --chown=mesa:mesa . /mesa
# source mesasdk
ENV MESASDK_ROOT=/mesa/mesasdk MESA_DIR=/mesa/mesa
RUN echo 'source $MESASDK_ROOT/bin/mesasdk_init.sh' >> $HOME/.profile
# install mesa
WORKDIR $MESA_DIR
RUN source $HOME/.profile && ./install

WORKDIR /mesa/work
