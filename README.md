# IOT-DATA-LOGGER-WITH-THRESHOLD-VIOLATION-DETECTION
This IoT-based data logger monitors temperature and humidity using a DHT11 sensor and LPC2148 microcontroller. It alerts users via buzzer when thresholds are exceeded, logs data, and uploads values to ThingSpeak. Setpoints are stored in EEPROM and can be updated locally via keypad or remotely via the cloud.

HARDWRAE REQUIREMENTS:
    • LPC2148
    • DHT11
    • AT24C256
    • 4x4 MATRIX KEYPAD
    • SWITCH
    • LCD
    • BUZZER
    • WI-FI MODULE (ESP01)
    • DB-9 CABLE/USB-UART CONVERTER

SOFTWARE REQUIREMENTS:
    • KEIL C Compiler
    • PROGRAMMING IN EMBEDDED C
    • Flash Magic
    
Key Features:
Real-time environmental monitoring
EEPROM-based persistent storage of threshold values
Alerts using buzzer on threshold violation
Cloud integration with Thingspeak for data logging
Remote configuration via cloud and local keypad
Interrupt-driven user input system 

Working principle:
The system initializes all peripherals (LCD, DHT11, EEPROM, ESP01, keypad, and buzzer).
* Setpoints are read from EEPROM during startup.
* The DHT11 sensor continuously measures temperature and humidity.
* These values are compared with the setpoints, and if a threshold is violated:
       The current value is sent to the Thingspeak cloud.
       The buzzer is activated with timed ON/OFF cycles to alert nearby personnel.
* Every 3 to 5 minutes, the system fetches the latest setpoints from the Thingspeak cloud.
* If the new setpoint differs from the current EEPROM value, the EEPROM is updated.
* If a local interrupt is triggered, the user can manually update setpoints using the keypad.
