# SYSC3303-Group-1
# Iteration 1

## Deliverables
* Source files (in `src` folder)
* Documentation
  - UML
  - UCM
* README.md
* README.txt


## Authors
- Kevin Sun (101000157)
- Cameron Rushton (101002958)
- Luke Newton (100999309)
- Ryan Ribeiro (100997936)
- Joe Frederick Samuel (100998314)

----------------------------
SOURCE FILES IN THIS PROJECT
----------------------------
Client.java: 
	represents the client in the system.
ErrorSimulator.java: 
	represents the intermediate host in the system.
ErrorSimMenuRunnable.java
	runs the main menu that takes input from the user.
ServerClientConnection.java
	represents a connection between a client and server for data transfer. spawned by error simulator.
InvalidCommandException.java
	menu invalid command exception
PacketDelayRunnable.java
	delays and then sends a packet while error sim thread still runs.
Server.java:
	represents the server in the system.
ServerSpawnThread.java
	thread spawned by server to process and respond to a received message.
ServerQuitRunnable.java
	thread spawned by server to allow user on server end to close server.
InvalidMessageFormatException.java
	represents an exception thrown when a ServerSpawnThread processes an invalid message

----------------------------------
EDITING PARAMETERS OF THE PROGRAMS
----------------------------------
At the top of Client.java, Server.java, and ErrorSimulator.java there are several constants defined which can be changed to alter the program.

1)Client.java
NUMBER_OF_CLIENT_MAIN_ITERATIONS:
	This integer value is the number of times the client will send out a request packet. Requests will always
	alternate between read and write, and the final request will always be invalid format.
INTERMEDIATE_HOST_PORT_NUMBER:
	This integer value is the port number that the ErrorSimulator will be found at.
	NOTE: if this value is changed in the client, it must be changed to the same value in the intermediate host(ErrorSimulator) as well!
MAX_PACKET_SIZE:
	This integer value specifies the maximum size of the data portion of a DatagramPacket.
FILENAME:
	This string value is the file name that is sent in each request.
MODE
	This string value is the mode that is sent in each request.
TIMEOUTS_ON:
	This boolean value specifies whether or not timeouts for receives are active for the client. Originally timeouts
	be on; set this value to false to deactivate them.
TIMEOUT_MILLISECONDS:
	This integer value sets the timeout length in milliseconds.
OP_RRQ: The TFTP OP Code for read request
OP_WRQ: The TFTP OP Code for write request
OP_DATAPACKET: The TFTP OP Code for data packet transmission
OP_ACK: The TFTP OP Code for acknowledging reception of packet.
OP_ERROR: The TFTP OP Code for notifying of failed packet transmission error.
	
2)ErrorSimulator.java
SERVER_PORT_NUMBER:
	This integer value is the port number that the server will be found at.
	NOTE: if this value is changed in the ErrorSimulator, it must be changed to the same value in the server
		  as well!
INTERMEDIATE_HOST_PORT_NUMBER:
	This integer value is the port number that the ErrorSimulator will be found at.
	NOTE: if this value is changed in the ErrorSimulator, it must be changed to the same value in the client
		  as well!
MAX_PACKET_SIZE:
	This integer value specifies the maximum size of the data portion of a DatagramPacket.
TIMEOUTS_ON:
	This boolean value specifies whether or not timeouts for receives are active for the client. Originally timeouts
	be on; set this value to false to deactivate them.
TIMEOUT_MILLISECONDS:
	This integer value sets the timeout length in milliseconds.
	
3)Server.java
SERVER_PORT_NUMBER:
	This integer value is the port number that the server will be found at.
	NOTE: if this value is changed in the server, it must be changed to the same value in the intermediate
		  host as well!
	NOTE: This value was specified to be 69 in the assignment
TIMEOUTS_ON:
	This boolean value specifies whether or not timeouts for receives are active for the client. Originally timeouts
	be on; set this value to false to deactivate them.
TIMEOUT_MILLISECONDS:
	This integer value sets the timeout length in milliseconds.
MAX_PACKET_SIZE:
	This integer value specifies the maximum size of the data portion of a DatagramPacket.

----------------------
TO RUN THE ASSIGNMENT
----------------------
See set up instructions in project report.
