Cordova plug-in development test project
==============

This project is mainly used to debug plug-in development, technology uses framework7 + requirejs + react + pubsubjs, so the project can be used as an integrated framework for development based.

#####Include tested plugins:
- [cordova-plugins-activity](https://github.com/cfansimon/cordova-plugins-activity)
- [cordova-plugin-ble-central](https://github.com/don/cordova-plugin-ble-central)
- [BluetoothSerial](https://github.com/don/BluetoothSerial)


#####Development Process:
- Preconditions: self-install nodejs, grunt, cordova-cli, babel
- Note: babel installation changes, as follows:
- npm install --global babel-cli
- npm install babel-preset-react

Install nodejs dependencies first
```bash
$ npm install
```
Shell into the www_src directory, start jsx real-time compilation, - compact compression (variable name is not compressed) --no-comments delete notes
```bash
babel --presets react src --watch --out-dir build --compact --no-comments
```
When you run the following command during the modification of the code, the browser display is automatically refreshed
```bash
$ grunt debug
```
After a stage of coding, run the following command, you can compress the merge part of the js source and html pages (www_src / src directory source code not compressed) to the root directory www directory
```bash
$ grunt build
```
Finally, the browser preview again to see if the compressed code has an error
```bash
$ grunt server
```
Complete the work, Android real machine debugging, remember to plug in the phone, then run the following command
```bash
$ cordova run
```

Special Note: js can not test the plug-in, you need to test android studio, such as Bluetooth plug-in, you can first use the following command to copy all the source code to android
```bash
$ grunt build-src && cordova build
```
And then the root directory under platform / android project into android studio to do development testing
# ECFMP
