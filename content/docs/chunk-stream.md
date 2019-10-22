---
title: "Chunk Stream Message Type"
weight: 3
menu: "docs"
---

<h1>Protocol References</h1>
RTMP spec, section 6.1 

```
    ---------------------------------------------------------------------
    |         |            |          |          |                      |
    |Msg type |Payload Len |timestamp |Stream ID |  Pay load            |
    | 1 Byte  | 3 bytes    |  4 bytes | 3 bytes  |  Size = Payload Len  |
    |         |            |          |          |                      |
    ---------------------------------------------------------------------
```

* 01: SetChunkSize
* 02: Abort
* 03: Ack Chunk
* 04: User Control Message
* 05: Window Ack Size
* 06: Peer Bandwidth
* 08: Audio Message
* 09: Video Message
* 15: Data Message (AMF3)
* 16: Shared Object Message (AMF3)
* 17: Command Message (AMF3)
* 18: Data Message (AMF0)
* 19: Shared Object Message (AMF0)
* 20: Command Message (AMF0)
* 22: Aggregate Message
