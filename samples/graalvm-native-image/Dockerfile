FROM amazon/aws-lambda-provided:al2.2021.03.22.18
ENV LANG=en_US.UTF-8
RUN yum install -y gcc gcc-c++ libc6-dev zlib1g-dev curl bash zlib zlib-devel zip tar gzip
ENV GRAAL_VERSION 21.0.0.2
ENV JDK_VERSION java11
ENV GRAAL_FILENAME graalvm-ce-${JDK_VERSION}-linux-amd64-${GRAAL_VERSION}.tar.gz
ENV GRAALVM_HOME /usr/lib/graalvm
RUN curl -4 -L https://github.com/graalvm/graalvm-ce-builds/releases/download/vm-${GRAAL_VERSION}/${GRAAL_FILENAME} -o /tmp/${GRAAL_FILENAME}
RUN yum install -y bsdtar
RUN bsdtar -zxf /tmp/${GRAAL_FILENAME} -C /tmp \
    && mv /tmp/graalvm-ce-${JDK_VERSION}-${GRAAL_VERSION} ${GRAALVM_HOME}
RUN rm -rf /tmp/*
RUN ${GRAALVM_HOME}/bin/gu install native-image
