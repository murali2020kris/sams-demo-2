FROM alpine:3.4
MAINTAINER 	Viktor Farcic <viktor@farcic.com>

RUN mkdir /lib64 && ln -s /lib/libc.musl-x86_64.so.1 /lib64/ld-linux-x86-64.so.2

EXPOSE 8080
ENV DB db
ENV SERVICE_NAME sams-demo
CMD ["sams-demo"]
HEALTHCHECK --interval=10s CMD wget -qO- localhost:8080/demo/hello

COPY sams-demo /usr/local/bin/sams-demo
RUN chmod +x /usr/local/bin/sams-demo
