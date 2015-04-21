# rfchat

A simple application for the arduino to use [[RadioHead|https://github.com/PaulStoffregen/RadioHead]] for chat functionality via the serial port. To compile it you will need the RadioHead library installed.

## Hardware
Hardware requirement is a module supported by the RF22 driver (e.g. RF2M23BP from HopeRF). For other rf modules supported by RdaioHead you have to adjust the line initializing the driver accordingly.

## Connection diagram
This is based on the documention of RadioHead
[[pictures/RFM23BP_connection.png]]

## Setup
### Command line
1. Install crosscompile toolchain
2. Install arduino libs
3. install the RadioHead library
4. Set the arduino board in the Makefile
5. Run `make` to build rfchat
6. Connect the arduino
7. Run `make upload`
8. Open a serial console to the arduino

### using the Arduino IDE
1. Copy rfchat.ino to your sketchbook directory
2. Install RadioHead library
3. Open rfchat.ino in the Arduino IDE
4. Select compile in the Arduino IDE
5. Connect the Arduino
6. Upload rfchat to the Arduino using the IDE


## Usage
After booting on the arduino you can connect to its serial port and simply type strings that then will be sent via the attached rf device. You will see the sent text prefixed with an indicator which ID you have and which ID the message is sent to, like e.g.

```
0->1
```

which means your ID is 0 and the recipent ID is 1. 
The same applies for messages you receive.

## Commands
To change the ID or the recipent you can use commands that have to start with '/'.

Commands are:

0 change own ID<br>
1 change recipent ID

e.g.

```
/023
```

will change your own ID to 23.

```
/124
```

will change the recipent ID to 24.

## Broadcasts
When setting the destination ID to 255, the sent message will be broadcasted to all reachable nodes. Note that with non broadcast addresses RadioHead does wait for confirmation on th received message from the destination. This does not apply for broadcast messages, you won't get a notification if the message reached a node.
