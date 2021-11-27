# Flash my CDEM

Use the `flash` script to flash your CDEM device from bash without the need to install Arduino IDE.

The script can download a tagged firmware release for you and flash it to the device.

This script can also be used to test your CDEM device.

## Install Dependencies

```bash
sudo apt install curl jq mosquitto-clients
```

* curl: http requests
* jq: parsing json
* mosquitto-clients: for subscribing to mqtt topic

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

## Automatic CDEM Test - EXPERIMENTAL

This is an early experimental script. May break any time. Only use at own risk and after reviewing the script.

```bash
./test
```

It was designed to test a batch of CDEM devices.

If the WiFi takes more than a minute to setup after a while, it might be because some `wpa_supplicant` processes are hanging around. A multi-kill can take care of that (at own risk again):

```bash
ps ax | grep wpa.conf | awk '{ print $1}' | xargs -L1 sudo kill
```