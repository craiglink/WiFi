# Modified WiFi Library

This is a modified version of the WiFi library from the [Arduino Espressif32 Framework](https://github.com/espressif/arduino-esp32.git).  The original code is from the 2.0.7 version of that
framework.

It adds a new WiFiClient::canWrite() method.  That method can be used to determine if
the TCP connection is ready to receive new data without blocking.  FluidNC needs that
feature to determine if a new status report can be sent over a WebSocket without stalling
the system.  This is used in conjunction with [a modified version of the
arduinoWebSockets library](https://github.com/MitchBradley/arduinoWebSockets#canSend)
