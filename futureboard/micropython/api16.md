# Programming with MicroPython: KOI

## Import KOI Library

Import SugarASR library to make use of its functions.

    from futureKOI import KOI

## KOI Basic Operations

### Initiate KOI

    koi = KOI(tx='P2',rx='P12',id=1)

Initiates the KOI port.

- tx: Tx Pin, use P2 for Robotbit Edu.
- rx: Rx Pin, use P12 for Robotbit Edu.

### Set KOI Camera Orientation

    # available modes
    # 0,2

    koi.screen_mode(mode, cmd='K6')

Sets the KOI camera orientation.

- mode: 0 for front, 2 for back

### Display text

    koi.text(x, y, delay, text, cmd="K4")

Displays a text on the KOI screen.

- x: X coordinate of the text.
- y: Y coordinate of the text.
- delay: Duration of the text in ms.
- text: The string to be displayed.

### KOI Screen Capture
    
    koi.screen_save(pic , cmd="K2")

Captures the screen and save to SD card.

- pic: Filename on the SD card in jpg format.

### KOI Displays JPG

    koi.screen_show(pic, cmd="K1")

Displays a jpg on the screen.

- pic: Filename on the SD card in jpg format.

## Face Detection

### Load Face Yolo

    koi.face_yolo_load(cmd="K30")

Loads the face yolo model.

### Single Face Detection

    x = koi.face_detect(cmd="K31")

Runs the single face detection.

### Obtain Face Coordinates

    koi.get_re(cmd="K31")[0]  #x
    koi.get_re(cmd="K31")[1]  #y

Returns the X or Y coordinate of the face detected.

### Multi Face Detection

    koi.face_count(cmd="K32")

Runs the multi face detection.

### Obtain Number of Faces

    koi.get_re(cmd="K32")[0]

Returns the number of faces detected.

## Machine Learning Image Classifier

### Initiate Image Classifier

    koi.init_cls()

Starts image classifier mode.

### Classifier Add Tag

    koi.cls_add_tag(tag,cmd="K41")

Add an image tag.

- tag: Name of the tag.

### Run Image Classifier

    koi.cls_run(cmd="K42")

Returns the tag for the classified object.

### Save the Classifier Model

    koi.cls_save_model(model,cmd="K43")

Saves the model to the SD Card.

- model: The filename on the SD card.

### Load a Classifier Model

    koi.cls_load_model(model="abc.json",cmd="K44")

Loads the model from the SD Card.

- model: The filename on the SD card.

## Colour Blob and Line Tracking

### Calibrate a Colour to Track

    koi.color_cali(name ,cmd="K16")

Calibrates a colour to track.

- name: The name for this colour.

### Tracks a Colour Blob

    koi.color_tracking(name="name", cmd="K15")
    # returns [cx,cy,w,h,name]

Returns a list containing the values of the colour blob.

- name: the name of the colour to track.

### Obtain Colour Blob Values

    koi.get_re(cmd="K15")[1] #cx
    koi.get_re(cmd="K15")[2] #cy
    koi.get_re(cmd="K15")[3] #w
    koi.get_re(cmd="K15")[4] #h

Returns the specific value of the colour blob.

### Tracks a line

    koi.line_tracking(name ,cmd="K12")
    # returns [x1, y1, x2, y2, name]

Returns a list containing the values of the line.

- name: the name of the colour to track.

### Obtain Line Values

    koi.get_re(cmd="K12")[1] #x1
    koi.get_re(cmd="K12")[2] #y1
    koi.get_re(cmd="K12")[3] #x2
    koi.get_re(cmd="K12")[4] #y2

Returns the specific value of the line.

## Shape Detection

### Circle Detection

    koi.circle_detect(threshold, cmd="K10")

Runs the circle detection.

- threshold: The threshold for circle, typical value is about 2000, adjust to achieve best results.

### Obtain Circle Values

    koi.get_re(cmd="K10")[0] #cx
    koi.get_re(cmd="K10")[1] #cy
    koi.get_re(cmd="K10")[2] #r

Returns the specific value of the circle.

### Rectangle Detection

     koi.rectangle_detect(th=4000,cmd="K11")

Runs the rectangle detection.

- threshold: The threshold for rectangle, typical value is about 1000, adjust to achieve best results.

### Obtain Rectangle Values

    koi.get_re(cmd="K11")[0]
    koi.get_re(cmd="K11")[1]
    koi.get_re(cmd="K11")[2]
    koi.get_re(cmd="K11")[3]

Returns the specific value of the rectangle.

## Code Scanner

### QR Code Scanner

    koi.scan_qrcode(cmd="K20")

Returns the QR Code data.

### Barcode Scanner

    koi.scan_barcode(cmd="K22")

Returns the Barcode data.

### Apriltag Scanner

    koi.scan_Apriltag(cmd="K23")

Runs the scanner for Apriltag.

### Obtains Apriltag data

    koi.get_re(cmd="K23")[0] #id
    koi.get_re(cmd="K23")[1] #cx
    koi.get_re(cmd="K23")[2] #cy
    koi.get_re(cmd="K23")[3] #w
    koi.get_re(cmd="K23")[4] #h

Returns the specific data of the Apriltag.

## Wifi Connection

### Connect to Wifi

    koi.connect_wifi(router ,pwd ,cmd="K50")

Connects to a Wifi network.

- router: The SSID.
- pwd: The password.

### Displays IP Address

    koi.get_ip(cmd="K54")

Displays the IP Address.

## BaiduAI

### BaiduAI Face Recognition

    koi.baiduAI_face_detect(cmd="K75")
    # returns [face token, age, sex, mask, emotion]

Returns a list of values from the BaiduAI Face Recognition.

### BaiduAI Face Token

    koi.get_re(cmd="K75")[0]

Returns the face token.

### BaiduAI Add Face to Group

    koi.baiduAI_face_add(face_token="token" ,groupName="group" ,faceName="name" ,cmd="K76")

Adds the face token to a group.

- face_token: The token to be added.
- groupName: The group name.
- faceName: The name of the person.

### BaiduAI Search Face in Group

    koi.baiduAI_face_search(face_token="token" ,groupName="group" ,cmd="K77")[0]

Searches the face in a group and returns the person name.

- face_token: The token to be searched.
- groupName: The group name.

### BaiduAi Text to Speech

    koi.baiduAI_tts(text ,cmd="K78")

Generates a speech using BaiduAI.

-text: The text to be spoken.

## Audio

### Record Wav File

    koi.audio_record(name)

Record and saves the wav file to the SD card.

- name: The file name in wav format.

### Play Wav File

    koi.audio_play(name)

Plays a wav file from the SD card.

- name: The file name in wav format.

### Calibrate Ambient Noise

    koi.audio_noisetap()

Calibrates the ambient noise for speech recognition.

### Speech Recognition Add Tag

    koi.speech_add_tag(tag)

Adds a speech tag.

- tag: The tag name.

### Get Speech Recognition Tag

    koi.speech_run(cmd="K65")

Runs the speech recognition and returns the tag.

### Save Speech Model

    koi.speech_save_model(file)

Saves the speech model to the SD card.

- file: The filename.

### Load Speech Model

    koi.speech_load_model(file)

Loads a speech model.

- file: The filename.

## Miscellaneous

### Reset KOI

    koi.reset(cmd='k99')

Resets the KOI.

### Stop Classifier and Face Yolo

    koi.stop_kpu(cmd='k98')

Stops the KPU from running Classifier and Face Yolo.