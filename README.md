# Android accelerometer

An example app that uses a digital filter to detect shaking the device

## Usage

When you open the app, you'll see the live values from the device's embedded accelerometer.
Below the digital display is an analog bar.
When you gently shake the device from side to side (X-axis) the analog bar will fill, showing full when consistent shaking is detected.
The bar will not show full when the device is merely tapped.

## Notes

This project was started in early 2010, in response to a SO question regarding detecting shake via the embedded accelerometer.
I found many of the answers unsatisfactory, as they were based on empirical timing, loops, and averaging.
From my engineering background I thought this would be better solved as a signal processing problem.
The basic idea was to use a bandpass filter to detect energies in the shake frequency ranges.

I searched online to refresh my mind on DSP principles.
I found a [really good source that covered it comprehensively](http://www.dspguide.com/ch19/3.htm).
In particular, one chapter covered bandpass and notch filters, with the recurrence equations and parameter computations.
To aid in the computations, I created a simple spreadsheet, which would help in adjusting the coefficients.

The sensor list is technically not part of the digital filter code.
I found it useful for looking up the details of the available sensors, which vary by device type.
On  Motorola XT1080, the accelerometer is LIS3DH 3-axis Accelerometer.

## Building and running

The source contains IntelliJ files to facilitate using that IDE.
It should be good to go if you have IntelliJ and the Android SDK configured.
