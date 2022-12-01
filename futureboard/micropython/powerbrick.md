# Programming with MicroPython: Powerbrick Modules

## Import Sugar Library

Import the Library to make use of its functions.

    from sugar import *

## RFID Sensor

### Scan RFID Tag

    RFID().probe() # Without callback
    RFID().probe(probeCallback if 'probeCallback' in dir() else None) # With callback

Begin the scan for an RFID tag. Can be used with event callback.

### Stop RFID Probing

    RFID().stop()

Stop the RFID probing.

### RFID UUID Value

    RFID().uuid() 