ARG BUILD_FROM
FROM $BUILD_FROM

ENV LANG C.UTF-8

# Install requirements for add-on
RUN apk add --no-cache git make g++ wiringpi-dev grep wget unzip

RUN git clone https://github.com/juanrodgil/hassio-flashcc2531/ && \
              cd hassio-flashcc2531 && \
              cd flashcc2531 && \
              make all

# Copy data for add-on
COPY run.sh /
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
