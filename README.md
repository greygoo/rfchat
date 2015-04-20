# rfchat

A simple application for the arduino to use [RadioHead|https://github.com/PaulStoffregen/RadioHead] for chat functionality via the serial port. To compile it you will need the RadioHead library installed.

## Hardware
Hardware requirement is a module supported by the RF22 driver (e.g. RF2M23BP from HopeRF). For other rf modules supported by RdaioHead you have to adjust the line initializing the driver accordingly.

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
