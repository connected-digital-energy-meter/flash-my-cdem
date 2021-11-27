# Flash my CDEM

Use the `flash` script to flash your CDEM device from bash without the need to install Arduino IDE.

The script can download a tagged firmware release for you and flash it to the device.

This script can also be used to test your CDEM device.

## Install Dependencies

```bash
sudo apt install curl jq
```

* curl: http requests
* jq: parsing json

Make sure you have `pyserial` and `esptool` installed as a python package:

```bash
pip install pyserial
pip install esptool
```

## Get this repo

```bash
cd ~
git clone https://github.com/connected-digital-energy-meter/flash-my-cdem.git
cd flash-my-cdem
```

## Starting the Wizard

Make sure no other application is using the device `/dev/ttyUSB0`.

Just execute the script and answer the questions asked to you:

```bash
./flash
```
