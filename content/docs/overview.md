---
title: "Overview"
weight: 1
menu: "docs"
---

<h1>Real Time Messaging Protocol Overview</h1>
<p>Real Time Messaging Protocol (RTMP) was designed to support very low-latency for interactive, multiparty applications with seamless integration of live or recorded video, as well as broadcast streaming, video on demand (VOD) use cases.</p>
<p>Messaging features:</p>
<ul>
<li>one or more audio, video and data streams</li>
<li>system and user-defined command messages</li>
<li>data synchronization (shared objects)</li>
</ul>
<p>RTMP supports multiple transports:</p>
<ul>
<li>TCP/IP, optionally with secure socket connection</li>
<li>HTTP/S</li>
<li>UDP via <a href="https://tools.ietf.org/html/rfc7425" rel="nofollow">RTMFP</a></li>
</ul>
<h3>Multiplexed Streams</h3>
<p>An RTMP connection multiplexes one or more streams. Each stream is a logical channel, carrying messages of one type for a single audio, video or data stream.</p>
<p>The protocol supports multiple synchronized audio, video and data streams; however some client or server implementations may limit the number or type of streams.</p>
<h4>Example use case</h4>
<p>A simple use case of audio-video streaming could include one audio stream and one video stream. The protocol enables each stream to be multiplexed such that small high frequency audio messages may be interleaved through multiple chunks representing a larger video frame. This stream construction allows a low-power client to prioritize audio playback and drop video data. For example, in the case of a device without hardware decompression, this allows using CPU for other operations infrequent operations without dropping audio which is typically more disruptive for a human audience.</p>
<h4>RTMP Chunk Stream</h4>
<p>When using a reliable, ordered transport protocol, such as TCP/IP, RTMP allows for low-latecy, interactive application by splitting larger messages into smaller "chunks" for multiplexed delivery.</p>
<p>Chunking allows small messages to be sent with less overhead, as the chunk header contains a compressed representation of information that would otherwise have to be included in the message itself.</p>
<p>For more detail, see <a href="https://github.com/veriskope/rtmp/blob/master/spec/spec/chunk-format" target="_blank">chunk format</a>.</p>
<h3>Initial Connection Sequence</h3>
<ol>
<li>Handshake (spec section 5.2)</li>
<li>Client Command Message: Connect</li>
<li>Bandwidth Coordination</li>
<li>Server Message: StreamBegin</li>
<li>Server Command Response: Connect success/failure</li>
</ol>
<h3>Command Messages</h3>
<p>A client or a server can make a Remote Procedure Call (RPC) using command messages to the peer.
Command messages carry AMF encoded commands between the client and the server.</p>
<p>TO DO: add detail here</p>
