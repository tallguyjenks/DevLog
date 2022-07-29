

`T`ransmission `C`ontrol `P`rotocol

## Initiation

Operates through a 3 way opening handshake

- Client [[terms.syn]] --> Server
- Server [[terms.syn]]-[[terms.ack]] --> Client
- Client [[terms.ack]] --> Server

---

1. The client sends a [[terms.syn]] segment to the server with a randomly generated sequence number. The client enters
the [[terms.syn]] state.
2. The server, currently in the LISTEN state (assuming it is online), responds with a [[terms.syn]]/[[terms.ack]] segment, containing its own randomly generated sequence number. The server enters the [[terms.syn]] state.
3. The client responds with an [[terms.ack]] segment. The client assumes the connection is ESTABLISHED.
4. The server opens a connection with the client and enters the ESTABLISHED state.

## Termination - Abrupt

Terminates communication abruptly with an [[terms.rst]] segment

## Termination - Graceful

Graceful exit to the connection is done through a 4-way handshake consisting of:

- Client [[terms.fin]] (enters [[terms.fin]]-WAIT1 state) --> Server
- Server [[terms.ack]] (enters CLOSE-WAIT state) --> Client
- Client (Receives [[terms.ack]] and enters [[terms.fin]]-WAIT2 state) --> Server
- Server [[terms.fin]] (enters LAST-[[terms.ack]] state) --> Client
- Client [[terms.ack]] (enters TIME-WAIT state) --> Server

---

1. The client sends a [[terms.fin]] segment to the server and enters the [[terms.fin]]-WAIT1 state.
2. The server responds with an [[terms.ack]] segment and enters the CLOSE-WAIT state.
3. The client receives the [[terms.ack]] segment and enters the [[terms.fin]]-WAIT2 state. The server sends its own [[terms.fin]] segment
to the client and goes to the LAST-[[terms.ack]] state.
4. The client responds with an [[terms.ack]] and enters the TIME-WAIT state. After a defined period, the client closes its connection.
5. The server closes the connection when it receives the [[terms.ack]] from the client.
