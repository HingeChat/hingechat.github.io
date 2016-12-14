Network
=======

This file will explain the entire Hinge networking system, and client connection in order.

First, a client will connect to the TURN server via the ConnectionManager which uses the 'sock' module. The ConnectionManager handles message sending and receiving to and from the TURN server.

The client John Smith will notify the ConnectionManager that it would like to connect to the client Rachel Adams with the HELO command (COMMAND_HELO in src.hinge.utils.constants).

John Smith will do this by packing a Message (see Message documentation) with the information it would like to pass on to the ConnectionManager.

The ConnectionManager will take the Message and pass it onto the server using the sock module. The server will accept the command and send it to Rachel Adams' ConnectionManager.

Her ConnectionManager will receive the Message including the HELO command and properly handle it. For more information on the Client handshake system, see CLIENT.md.