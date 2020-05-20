FROM ubuntu:18.04

WORKDIR /app
COPY pdfresurrect-0.19 /app/pdfresurrect-0.19

RUN apt-get update && apt-get install -y gcc && apt-get install -y build-essential
RUN cd pdfresurrect-0.19 && ./configure && make && make install

COPY exploit.pdf /app/exploit.pdf

ENTRYPOINT pdfresurrect exploit.pdf

