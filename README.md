# EyeHear

A techForGood project to display speech-to-text on a wearable low-cost device.

![Photograph of a person trying on EyeHear](https://lh3.googleusercontent.com/xY2p5IFlahQVqTHxMlVxTIqvuSGSWfXkXjcX6KWwQlT-XfomVlsuo6OfEbGvWgwLYAjNCRV3iCadXBp7Y9l78b-m-ng_QzZ_ys7mr8hN24RALn1Ki4ZrSGYV_iX-_ShcDZptNtMAYkslIq_05rZMiux6zqL0hz2nEtFp13rg-QNVuhPnNEem8MsDgTo2zwWuq2i1JV62FsoKM9Vw_k-1MaGZnDMrOHkhQlxMvV8RdaauM6bTKF00kf-JX6LOL_w8mwf6VFvsyoyRdBKB0C1Ri8jqBfjDWXhiHSrvpCz876_QAKmXic1TBcgjSufY0txeS0uhMXsYCVKQZpK7ZFA5tkWWiFjmC8GVPv8qO8N0yMKFA3Yy8awjMMfYMRatJH8U1rLZhjNLpt6jYd0uJWztqkKUDeMtm1fEtr7Ychk4FEKTcmSwut2hDwpom3AfpToG13_deOQQDuCVcuHM3KeNp1Dwkpvk2vY52khA3u3z79OOUfohUMrg5b0koG9EIeigZ6xSxOS2uivy_2hraktmZQIiDYfifqUV-kl-U8FTS3z7Q8PQ2Z3QoVFOEBCP10eMhUPxW0aCltN-gqYYAGgZUn7P82lci8tKge0EaYRSAW8n2LjrfOLvPff9CsbX-1goLBhQGj7-0WOdzjDEoJEjACJtf49704Twr9Qygj0HLFhtGMfC4n2lDCR_2U_kk4j8KPdbnX69lLZlLO1ZDT3Ne6JR0nSSMoV3LXFLspbkE1OSUYjktAAoZaIAW-k=w1713-h1284-no?authuser=0) 

## Introduction

We are a group of volunteers working with the hard of hearing community in Singapore to develop a wearable device that displays speech as text to facilitate their participation in face to face interactions. 

Currently, the Hard-Of-Hearing community uses speech-to-text apps to tell what is being said during a conversation. However, from our discussions with our community partner, it has come to our attention that these conventional methods of communication used by the deaf and hard of hearing pose a limitation where it is inconvenient and inefficient for them to keep looking at an app on their phone during a conversation. They will not be able to maintain eye contact with others during the conversation, thus limiting their ability to engage in face-to-face communication. As face-to-face conversations are part of our daily lives, this limitation proves to be a major problem which we aim to solve.

Here's a quick demo of the device:


https://user-images.githubusercontent.com/26520389/167285186-1b3ce4cc-87e0-46ce-ad81-fe2cdca50757.mp4



### Timeline
<details>
  <summary>Version 1: 3D printed case, mounted to a pair of goggles. Webapp to WeMOS microcontroller.</summary>
  
![Image of the first version of Eyehear which is a pair of goggles with a case attached on the side to hold the electronic parts](https://user-images.githubusercontent.com/26520389/167285395-4d4f819b-4874-437e-946b-3f25db9d0a77.jpeg)
  
![A user wearing EyeHear version 1](https://user-images.githubusercontent.com/26520389/167285410-7dd594d4-62fc-4eb9-a970-ce2812e5c755.jpeg)
  
  ![eyehear version 1 detailed annotation of what is inside the case](https://user-images.githubusercontent.com/26520389/167285868-8d0e7d31-f54d-4d39-ae15-63afcf455d7b.PNG)

  How it worked:
  * ESP8226 continually runs a script that collects audio and sends it to our server hosted on AWS
* Server uses Google speech-to-text API to convert incoming audio into text, and send that text back to the ESP8226
* ESP8226 displays the translated text on the screen, which is reflected by the mirrors and appears in front on the user’s eyeline


</details>

<details>
  <summary>Version 2: Hardware mounted on head strap for spectacles. Webapp + WeMOS integration.</summary>

  ![A pair of glasses with a chopstick taped to the side and the electronics taped in front to hold the speech to text screen](https://user-images.githubusercontent.com/26520389/167285548-c3c389f9-d752-48bb-b8fe-47f216c7236e.jpeg)
  


</details>

<details>
  <summary>Version 3: Raspberry Pi 0 to be integrated with a speech-to-text software solution.</summary>

  ![a couple of version 3 eyehear arranged in a row on top of a black table](https://user-images.githubusercontent.com/26520389/167285908-d9c641a8-3996-443e-938c-c170e1de08fc.PNG)

  Changes made:
  * L-shaped open design
  * Various designs customised for each tester
  * Using a Raspberry Pi instead, which continually runs a script that collects audio and converts it into text using Google speech-to-text API. The text is then displayed on the screen, directly in front of the user’s eyeline


</details>

### Future feature ideas:
* Improve speech-to-text model’s accuracy - We could train a new model that would recognise Singaporean / SEA Speech Patterns better and provide a more accurate translation 
* Use an Offline Model - Current prototype requires internet access due to usage of API 
* Enable languages beyond English -  Provide support for different languages so that more users can use ‘EyeHear’
* Other ideas are welcome!


## Quick Setup

```bash
# Copy GOOGLE_APPLICATION_CREDENTIALS file to /home/pi/
# Then
./setup.sh
```

## Get started

> This project requires python3, you may need to replace command `python` to `python3` and `pip` to `pip3`.

<details>
  <summary>Install Python</summary>
  
```bash
sudo apt-get update
sudo apt-get install -y build-essential python-dev python-rpi.gpio python-spidev python-pip python-pil python-numpy raspberrypi-kernel-headers
sudo apt install libportaudio2
```

</details>

<details>
  <summary>Install prerequisities</summary>

```bash
pip3 install -r requirements.txt
```

</details>

```bash
export GOOGLE_APPLICATION_CREDENTIALS="/home/pi/your_google_cloud_application_credential.json"

git clone https://github.com/Engineering-Good/eyeHear.git
cd eyeHear
python3 eyeHear/main.py
```

## Hardware

<details>
  <summary>Raspberry Pi Zero</summary>

- 1GHz CPU
- 512MB RAM

</details>

<details>
  <summary>Screen Display</summary>

- Resolution: 128x64
- ![1.3-inch 240x240 IPS LCD Breakout - ST7789](https://sg.cytron.io/p-1.3-inch-240x240-ips-lcd-breakout-st7789)

</details>

<details>
  <summary>Microphone</summary>

- ![USB Microphone](https://www.adafruit.com/product/3421)

</details>

<details>
  <summary>Frame</summary>

- ![Hollow fiberglass rod](https://www.passionkites.com/0.6cm-hollow-fiberglass-rod-1.5m/)

</details>

  
