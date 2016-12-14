Message
=======

The Message module (src.hinge.network.Message) is what ConnectionManagers (src.hinge.network.ConnectionManager) use to handle data coming to and from the server.

A Message can contain the following pieces of data, a serverCommand, a clientCommand, a sourceNick, a destNick, a payload, an hmac, an error, a num, an isGroup, and otherNicks.

serverCommand: a command sent from the ConnectionManager to the server that is intended for the server (like registering a nick or adding a nick to a group chat). The server will then send a Message back to the client with the data that is necessary.

clientCommand: a command sent from the ConnectionManager to the server that *won't* be handled by the server, but still be sent to the other client.

sourceNick: the nick/client that the Message came from.

destNick: the nick/client the Message is going to.

payload: the data to be sent to the destNick.

hmac: the hmac key to decrypt the data (the SMP (Socialist Millionaire Protocol) is in place to detect MITM attacks but not prevent them, which is why there is a feature for nicks to authenticate themselves).

error: the error if the Message is invalid.

num: the specific number of the Message.

isGroup: a boolean that decides if the Message is for a group chat or not.

otherNicks: if it's for a group chat, the other nicks will be involved with the Message.
