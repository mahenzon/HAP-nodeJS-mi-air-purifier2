# HAP-nodeJS module to take control of Mi Air Purifier 2 through HomeKit (including Siri)


## Features

- [x] Show and toggle power
- [x] Switch between Favorite, Auto, Silent and Idle modes
- [x] Show sensors data (temperature, relative humidity, air quality (relative and PM2.5))
- [x] Get updates on events (mode and power state change, new data on sensors)
- [x] Change fan speed
- [x] Blink LED on `identify` event

___
# HOW TO:

- **Make sure you have HAP-NodeJS installed**
- **Make sure you have NodeJS version >= 8** (tested on 9.4.0)
- Go to HAP-NodeJS folder and run `npm install miio` (tested on 0.15.4)
- Save [MiAirPurifier2_accessory.js](https://github.com/surik00/HAP-nodeJS-mi-air-purifier2/blob/master/MiAirPurifier2_accessory.js) to the `HAP-NodeJS/accessories` folder
- Run `miio discover --sync` in terminal, wait for something to be printed in terminal. If there are any miIO devices, it will discover it. Output looks like this:

```bash
root@minibian[rw]:~/Documents/HomeKit/HAP-NodeJS$ miio discover --sync
 INFO  Discovering devices. Press Ctrl+C to stop.

Device ID: 12345678
Model info: zhimi.airpurifier.m1
Address: 192.168.1.77
Token: 2b26525b0674c61e1893bc74fd2f38d6 via auto-token
Support: At least basic
```

You need device's IP address. And it will be better to save token too, because it may be hidden with future device's software updates.

*I recommend to make a reservation on your Wi-Fi router for your device.*

- Edit `MiAirPurifier2_accessory.js` file's lines: you have to provide unique mac address (just use device's one) in `username` and device's IP address in `address`. Mac address has to be unique to let HomeKit remember devices.
- Optional: edit `serialNumber`, `firmware` and `token`.
- On line 38 set accessory mode. Default is 3

- Run HAP-nodeJS server!

___


### This project couldn't be possible without these cool libraries:
* **[HAP-NodeJS](https://github.com/KhaosT/HAP-NodeJS)** — a Node.js implementation of HomeKit Accessory Server.
* **[miIO Device Library](https://github.com/aholstenson/miio)** — Control Mi Home devices that implement the miIO protocol, such as the Mi Air Purifier, Mi Robot Vacuum and Mi Smart Socket. These devices are commonly part of what Xiaomi calls the Mi Ecosystem which is branded as MiJia.