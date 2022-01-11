---
id: DWLSqzKq9wyBVlDBR6sBr
title: Tcp
desc: ''
updated: 1641873548171
created: 1641872711679
---

`T`ransmission `C`ontrol `P`rotocol

Operates through a 3 way opening handshake

- Client [[terms.syn]] --> Server
- Server [[terms.syn]]-[[terms.ack]] --> Client
- Client [[terms.ack]] --> Server

1. The client sends a [[terms.syn]] segment to the server with a randomly generated sequence number. The client enters
the [[terms.syn]] state.
2. The server, currently in the LISTEN state (assuming it is online), responds with a [[terms.syn]]/[[terms.ack]] segment, containing its own randomly generated sequence number. The server enters the [[terms.syn]] state.
3. The client responds with an [[terms.ack]] segment. The client assumes the connection is ESTABLISHED.
4. The server opens a connection with the client and enters the ESTABLISHED state.

Terminates communication abruptly with an [[terms.rst]] segment

Graceful exit to the connection is done through a 4-way handshake consisting of:

