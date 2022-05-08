# EyeHear

A techForGood project to display speech-to-text on a wearable low-cost device.

![Photograph of a person trying on EyeHear](https://lh3.googleusercontent.com/xY2p5IFlahQVqTHxMlVxTIqvuSGSWfXkXjcX6KWwQlT-XfomVlsuo6OfEbGvWgwLYAjNCRV3iCadXBp7Y9l78b-m-ng_QzZ_ys7mr8hN24RALn1Ki4ZrSGYV_iX-_ShcDZptNtMAYkslIq_05rZMiux6zqL0hz2nEtFp13rg-QNVuhPnNEem8MsDgTo2zwWuq2i1JV62FsoKM9Vw_k-1MaGZnDMrOHkhQlxMvV8RdaauM6bTKF00kf-JX6LOL_w8mwf6VFvsyoyRdBKB0C1Ri8jqBfjDWXhiHSrvpCz876_QAKmXic1TBcgjSufY0txeS0uhMXsYCVKQZpK7ZFA5tkWWiFjmC8GVPv8qO8N0yMKFA3Yy8awjMMfYMRatJH8U1rLZhjNLpt6jYd0uJWztqkKUDeMtm1fEtr7Ychk4FEKTcmSwut2hDwpom3AfpToG13_deOQQDuCVcuHM3KeNp1Dwkpvk2vY52khA3u3z79OOUfohUMrg5b0koG9EIeigZ6xSxOS2uivy_2hraktmZQIiDYfifqUV-kl-U8FTS3z7Q8PQ2Z3QoVFOEBCP10eMhUPxW0aCltN-gqYYAGgZUn7P82lci8tKge0EaYRSAW8n2LjrfOLvPff9CsbX-1goLBhQGj7-0WOdzjDEoJEjACJtf49704Twr9Qygj0HLFhtGMfC4n2lDCR_2U_kk4j8KPdbnX69lLZlLO1ZDT3Ne6JR0nSSMoV3LXFLspbkE1OSUYjktAAoZaIAW-k=w1713-h1284-no?authuser=0) 

## Introduction

We are a group of volunteers working with the hard of hearing community in Singapore to develop a wearable device that displays speech as text to facilitate their participation in face to face interactions. 

Currently, the ard-Of-Hearing community uses speech-to-text apps to tell what is being said during a conversation. However, from our discussions with our community partner, it has come to our attention that these conventional methods of communication used by the deaf and hard of hearing pose a limitation where it is inconvenient and inefficient for them to keep looking at an app on their phone during a conversation. They will not be able to maintain eye contact with others during the conversation, thus limiting their ability to engage in face-to-face communication. As face-to-face conversations are part of our daily lives, this limitation proves to be a major problem which we aim to solve.

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

git clone https://github.com/salvagegarden/eyeHear.git
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
  <summary>Display: SSD1306</summary>

- Resolution: 128x64

</details>

<details>
  <summary>Microphone</summary>

- USB Microphone

</details>
