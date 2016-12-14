Server Documentation
====================

The Hinge API uses a builtin central TURN server, which every client connects to via the builtin 'sock' module.

They do not use  the sock module directly, they use the ConnectionManager to handle message sending and receiving. The server can see every client and handles commands.

For example, when a client connects to another client, it will send the 'HELO' command, and the server will pass it on to the other client with the ConnectionManager as the messenger.

The ConnectionManager uses the Message module to pack messages, and the TURN server will read it. For more information about commands, see CONSTANTS.md.