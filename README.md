# rfchat

A simple application for the arduino to use [RadioHead|https://github.com/PaulStoffregen/RadioHead] for chat functionality via the serial port. To compile it you will need the RadioHead library installed.

Hardware requirement is a module supported by the RF22 driver (e.g. RF2M23BP) from HopeRF. For other rf modules supported by RdaioHead you have to adjust the line initializing the driver accordingly.

After booting on the arduino you can connect to its serial port and simply type strings that then will be sent via the attached rf device. You will see the sent text prefixed with an indicator which ID you have and which ID the message is sent to, like e.g.

```
0->1
```

which means your ID is 0 and the recipent ID is 1. To change the ID or the recipent you can use commands that have to start with '/'.

Commands are:

0 change own ID
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
