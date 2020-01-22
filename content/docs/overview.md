---
title: "Overview"
weight: 1
menu: "docs"
---

Real Time Messaging Protocol (RTMP) was designed to support very low-latency for
interactive, multiparty applications with seamless integration of live or
recorded video, as well as broadcast streaming, video on demand (VOD) use cases.

The protocol enables each stream to be multiplexed such that small high
frequency audio messages may be interleaved through multiple chunks representing
a larger video frame. This stream construction allows a low-power client to
prioritize audio playback and drop video data. For example, in the case of a
device without hardware decompression, this allows using CPU for other
operations infrequent operations without dropping audio which is typically more
disruptive for a human audience.

Messaging features:
- one or more audio, video and data streams
- system and user-defined command messages
- data synchronization (shared objects)

RTMP supports multiple transports:
* TCP/IP, optionally with secure socket connection
* HTTP/S
* UDP via [RTMFP](https://tools.ietf.org/html/rfc7425)

## Multiplexed Streams

An RTMP connection multiplexes one or more streams. Each stream is a logical
channel, carrying messages of one type for a single audio, video or data stream.

The protocol supports multiple synchronized audio, video and data streams;
however some client or server implementations may limit the number or type of
streams.

The most common implementations of RTMP are over TCP/IP, which is the initial
focus of this documentation.

## Reliable Transport

When using a reliable, ordered transport protocol, such as TCP/IP, RTMP allows
for low-latecy, interactive application by splitting larger messages into
smaller "chunks" for multiplexed delivery.

### RTMP Chunk Stream

Chunking allows small messages to be sent with less overhead, as the chunk
header contains a compressed representation of information that would otherwise
have to be included in the message itself.

For more detail, see [chunk format](spec/chunk-format).

### Initial Connection Sequence

1. Handshake (spec section 5.2)
2. Client Command Message: Connect
3. Bandwidth Coordination
4. Server Message: StreamBegin
5. Server Command Response: Connect success/failure

## Command Messages
A client or a server can make a Remote Procedure Call (RPC) using command
messages to the peer. Command messages carry AMF encoded commands between the
client and the server.

TO DO: add detail here
