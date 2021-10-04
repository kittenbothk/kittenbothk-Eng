# Programming with MicroPython: urequests & ujson

Please refer to official documentation for urequests and ujson for more details.

## Import FutureBoard Library

Import the Library to make use of its functions.

    from future import *
    
## 08:  urequests & ujson

## Import urequests and ujson

    import urequests
    import ujson
    
### 1. Get Data from API

    r=urequests.get(api_url)
    data=ujson.loads(r.content)
    
Paste the GET request url of the API into the api_url parameter.

Extract the data from parameter data.