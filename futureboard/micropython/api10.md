# Programming with MicorPython: Wireless Radio

## Import FutureBoard Library

Import the Library to make use of its functions.

    from future import *
    
## 10: Wireless Radio

## Import Radio Library

    from radio import *
    
### 1. Initiate a Radio

    r=Radio(trigger)
    
Define an event trigger function and call it in the trigger parameter to automatically call the function on receiving message.

### 2. Set the radio channel

    r.channel=1

### 3. Read the channel feed

    r.read()

Returns the message.
    
### 4. Publish a message to channel

    r.send(msg)
    
### Sample Program 1

    import time
    from radio import *
    
    r = Radio()
    print('channel', r.channel)
    r.channel = 12 
    
    while True:
        time.sleep(1)
        a = r.read()
        if a:
            print('get', a)
            
### Sample Program 2: Event Triggers

    from radio import *
    
    def onmsg(msg, mac):
        print('get', msg, 'from', mac)
    
    r = Radio(onmsg)
    print('channel', r.channel)
    r.channel = 12
    r.send("hello world")
   
   
### Advanced Program: MESH with ESPNOW

    # 1. WiFi
    import network
    w0 = network.WLAN(network.STA_IF)
    w0.active(True)
    
    # 2. MAC Address
    mac = w0.config('mac')
    >>> mac
    b'\xc4O3"\xdb\x89'
    
    # 3. import espnow
    from esp import espnow
    e = espnow.ESPNow()
    e.init()
    
    # 4. Add peer MAC Address
    # Note: Add the addess of the peer device
    e.add_peer(b'\x8c\xaa\xb5\xb9\xf8\xf0')
    
    # 5. Event Trigger
    def rxcb(mac, msg):
        print("Recv:", mac, msg)
    e.on_recv(rxcb)
    
    # 6. Publish
    e.send(b'\x8c\xaa\xb5\xb9\xf8\xf0', 'hello world')
    
    # Seeable on receving end
    # Recv: b'\xc4O3"\xdb\x89' b'hello world'
