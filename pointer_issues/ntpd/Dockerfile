FROM ubuntu:18.04

WORKDIR /app
COPY ntpsec-1.1.2 /app/ntpsec-1.1.2

RUN cd ntpsec-1.1.2 && apt-get update && ./buildprep && ./waf configure && ./waf build && ./waf install

COPY ntp.conf /etc/ntp.conf
COPY ntp.keys /etc/ntp.keys

EXPOSE 123

ENTRYPOINT ntpd -n -c /etc/ntp.conf
