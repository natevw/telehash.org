# HTTP Network Paths

When UDP is not available, switches may support a fallback `HTTP` path.  This is primarily useful when telehash is running inside a browser, or when an app needs to operate inside a highly restricted network that offers only HTTP.

This path is implemented using [socket.io](http://socket.io), and the only information needed to be exchanged in an `paths` is a `{"type":"http","http":"http://1.2.3.4:5678/"}`.

The `socket.io` interface is a minimal "packet" event being generated by either side, with it's arguments being a single object of `{"data":"base64-encoded-packet"}` where the raw binary telehash packet is base64'd and included as a data key/value.