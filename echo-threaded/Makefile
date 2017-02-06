CC=gcc
CFLAGS=-ggdb

all: server

server: TCPEchoServer-Thread.c DieWithMessage.c TCPServerUtility.c AddressUtility.c
	$(CC) $(CFLAGS) -o server TCPEchoServer-Thread.c DieWithMessage.c TCPServerUtility.c AddressUtility.c

clean:
	rm -rf client server server-timeout client.dSYM server.dSYM server-timeout.dSYM
