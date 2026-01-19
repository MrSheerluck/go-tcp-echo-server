# Go TCP Echo Server

A simple TCP echo server written in Go that listens for incoming connections and echoes back any received messages.

## Overview

This is a basic TCP server implementation that demonstrates concurrent connection handling using goroutines. The server accepts text input from clients, prefixes it with "Echo: ", and sends the response back.

## Building

```bash
go build -o go-tcp-echo
```

## Running

```bash
./go-tcp-echo <port>
```

Or directly:

```bash
go run main.go <port>
```

Replace `<port>` with the desired port number (e.g., `8080`, `9000`).

### Example

```bash
go run main.go 5000
```

The server will output:
listening on [::]:5000

## Usage

Connect to the server using a TCP client (e.g., `nc`, `telnet`) and send text:

```bash
echo "Hello" | nc localhost 5000
Output:

Echo: Hello
How It Works
The server listens for TCP connections on the specified port
Each incoming connection is handled concurrently in its own goroutine
The server reads lines from the client (terminated with \n)
Each line is echoed back with "Echo: " prepended
The connection closes when the client disconnects or an error occurs
Requirements
Go 1.24.2 or later

This README covers the basic purpose, how to build and run it, usage examples, and a brief explanation of how the server works.
```
