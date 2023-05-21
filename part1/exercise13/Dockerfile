FROM  golang:1.16

EXPOSE 8080
WORKDIR /usr/src/app

COPY ./example-backend/ .

RUN go build

ENV PORT=8080
ENV REQUEST_ORIGIN=https://example.com

CMD ["./server"]