---
id: DWLSqzKq9wyBVlDBR6sBr
title: Tcp
desc: ''
updated: 1641872896615
created: 1641872711679
---

`T`ransmission `C`ontrol `P`rotocol

Operates through a 3 way handshake

1. The client sends a SYN segment to the server with a randomly generated sequence number. The client enters
the SYN-SENT state.
2. The server, currently in the LISTEN state (assuming it is online), responds with a SYN/ACK segment,
containing its own randomly generated sequence number. The server enters the SYN-RECEIVED state.
3. The client responds with an ACK segment. The client assumes the connection is ESTABLISHED.
4. The server opens a connection with the client and enters the ESTABLISHED state.
