# Build stage
FROM golang:alpine AS build

WORKDIR /app

RUN go mod init desafio

COPY ./desafio.go .

RUN go build ./desafio.go && \
  rm go.mod && \
  rm desafio.go

# Final Stage
FROM scratch

WORKDIR /app

COPY --from=build /app /app

CMD [ "./desafio"]