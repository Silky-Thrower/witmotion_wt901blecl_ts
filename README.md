# WITMOTION WT901BLECL
Here is a small web application for using the WT901BLECL sensor (via USB and bluetooth) using react and TypeScript. All information about the sensor is located [here](https://github.com/WITMOTION/WT901BLECL). In addition to this documentation, I advise you to look at the documentation for the sensor used in the sensor [WT901](https://images-na.ssl-images-amazon.com/images/I/B11fVGszLsS.pdf).

## 1 Start the program
The program is launched via npm. The application will be available in the browser via the link: http://127.0.0.1:3000/.
```
npm start
```

To connect via Bluetooth on Linux, check if the **Web Bluetooth API** is available/enabled in your browser. To do this you can use the following steps:

1. Open a new tab in your browser.
2. In the address bar, enter "chrome://flags" (for Chrome) or "about:config" (for Firefox).
3. Look for the "Web Bluetooth" parameter and make sure it is enabled (replace default/disable with enable).
4. Then enter "chrome://bluetooth-internals" (for Chrome) or "about:bluetooth" (for Firefox).
5. If you see the "Devices" and "Services" section, then your browser supports the Web Bluetooth API.

If you are using a different browser, you can check the list of supported browsers on the Web Bluetooth Community Group site.
 
## 2 Notes

### 2.1 Documentation
If you need to change the sensor configuration, I advise you to immediately look at the documentation of the built-in sensor [WT901](https://images-na.ssl-images-amazon.com/images/I/B11fVGszLsS.pdf). The "native" documentation lacks a lot of things.

### 2.2 Sensor calibration

1. Calibration of the accelerometer and gyroscope occurs within 3 seconds after sending the command (no difficulties, just don’t touch it).
2. Magnetometer calibration involves rotating the sensor around its axes 3 times (see [video](https://youtu.be/smi2uePvC-Q?t=104))

### 2.3 Difficulties

For this sensor (by default), positioning occurs by reading data from 9 degrees (along the XYZ axes: 3 accelerometers, 3 gyroscopes, 3 magnetometers). Before calibrating the magnetometer, the angle oZ always gave the same value. After calibration, the oZ angle works adequately UNTIL ANY sharp linear shock (~ 1g) of the sensor. I don’t know whether it’s a marriage or not. I strongly advise you to forget about the magnetometer and IMMEDIATELY switch the sensor by 6 degrees.

## 3 Another version
In addition, there is a [repository](https://github.com/LiDline/witmotion_WT901BLECL_py), where this web application is implemented in python and plotly dash.
