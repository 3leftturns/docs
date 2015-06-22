---
word: Start
title: Getting started
order: 2
columns: 2
---

#Getting Started

## Getting to Know You

![]({{assets}}/images/family-portrait.png)

Congratulations on being the owner of a brand new Particle Device! Go ahead and open the box. You can see the different [contents](/datasheets/kits) and check out their [hardware datasheets](/datasheets) if you like! Let's quickly go over what you see.

####What's on it?

**The Microcontroller.** The microcontroller is the brain of your device. It runs your software and tells your prototype what to do. Unlike your computer, it can only run one application (often called *firmware* or an *embedded application*). This application can be simple (just a few lines of code), or very complex, depending on what you want to do. The microcontroller interacts with the outside world using pins.

**The Pins.** Pins are the input and output parts of the microcontroller that are exposed on the sides of your device. GPIO pins can be hooked to sensors or buttons to listen to the world, or they can be hooked to lights and motors to act upon the world. There are also pins to allow you to power your device, or power motors and outputs outside of your device. There are pins for Serial/UART communication, and a pin for resetting your device. Read about your pins [here](http://docs.spark.io/hardware/#spark-core-datasheet-pins-and-i-o).

**The Wi-Fi Module.** This is probably why you bought your device-- the Wi-Fi module allows your Core or Photon to communicate with the internet. It connects your device to the internet in the same way that your smartphone might connect to a wifi network. On the Photon, the Wi-Fi module is the same chip as the microcontroller.

**Buttons and LEDs.** Your device tells you what is going on using its RGB LED. You can give it some instructions (factory reset, erase wifi networks, etc) using the RST and MODE buttons. There's also a nice blue LED on your device that you can control with the D7 pin.

For more technical details on what comes on your device, go [here](/datasheets).

####Okay great, I want to play with it I want to make it do a thing right now!

Good, me too! Let's get started.

##Hello World!
In this example, we will connect your device to the internet for the very first time. Then, we will blink the D7 LED on your device by using your smartphone. If you don't have your smartphone with you, go ahead and move to the next lesson on [connecting over USB.](/guide/photon/connect)

####Materials
* **Hardware**
    * Your Particle device, brand new and out of the box!
    * USB to micro USB cable (included with Photon Kit, Maker Kit, and Core)
    * Power source for USB cable (such as your computer, USB battery, or power brick)
    * Your iPhone or Android smartphone
* **Software**
    * **For Photon**: Particle Mobile App - [iPhone](https://itunes.apple.com/us/app/particle-build-photon-electron/id991459054?ls=1&mt=8) | [Android](https://play.google.com/store/apps/details?id=io.particle.android.app)
    * **For Core**: Spark Core Mobile App - [iPhone](https://itunes.apple.com/us/app/spark-core/id760157884) | [Android](https://play.google.com/store/apps/details?id=io.spark.core.android)
* **Experience**
    * None! This is your first Blueprint.

####Step 1: Power On Your Device
![plug in your device!]({{assets}}/images/photon-plugged-in.jpg)

Plug the USB cable into your power source. (Your computer works perfectly for this purpose.)

#### 
*Learning Note: I've got the powerrrrrr!!!*

*Although you may be plugging it into your computer,  your device doesn't need the computer to learn to connect to the internet. Right now, it's just using it for power. You could just as easily power your device with a power brick, a battery shield, or another power source wired to the VIN pin.*
#### 

As soon as it is plugged in, the RGB LED on your device should begin blinking blue.

If your device is not blinking blue, hold down the "MODE" button for three seconds to reset.

If your device is not blinking at all, or if the LED is burning a dull orange color, it may not be getting enough power. Try changing your power source or USB cable.

####Step 2: Connect With Your Smartphone

#### 
*Learning Note: What happens when my device wants to talk to the internet?*

*When your device comes to life for the first time, it has a specific set of objectives:*
* *Find wifi*
* *Connect to wifi*
* *Execute firmware*

*Unless you tell it not to, your device will run through these commands every time you power it on. You can teach it different wifi networks using your phone or computer. It remembers up to 7 wifi networks, and it will connect to these automatically if it can find them.*

*When you power on your device for the very first time, though, it doesn't know any networks. It blinks blue, which is its way of saying, "Hey, I'm ready to find some wifi." Let's help it out.*
#### 

Open the app on your phone. Log in or sign up for an account with Particle if you don't have one.

Follow the instructions on the screen to connect your Core or Photon. Remember that to connect the Core, you need the older Spark Core app and to connect the Photon you need the new Particle App.

This may take a little while- but don't worry. If you have a Core, it will go through the following colors:

* *Blinking blue:* Listening for Wi-Fi credentials
* *Solid blue:* Getting Wi-Fi info from app
* *Blinking green:* Connecting to the Wi-Fi network
* *Blinking cyan:* Connecting to the Spark Cloud
* *Blinking magenta:* Updating to the newest firmware
* *Breathing cyan:* Connected!

If you are having trouble connecting, that's okay! Read over this example quickly, and then check out the [next lesson](/guide/photon/connect) to connect your device using the USB cable.

Once you have connected your device, it has learned that network. Your device can store up to seven networks. If you feel like your device has too many networks on it, you can wipe your device's memory of any wifi networks it has learned. You can do so by continuing to hold the MODE button for 10 seconds until the RGB LED flashes blue quickly, signaling that all profiles have been deleted.

####Step 3: Blink an LED!
The Spark app should now be on the Tinker screen, as shown for the Particle app below. The Spark Core App looks a bit different but works in basically the same way.

![Tinker on your Phone!]({{assets}}/images/tinker.png)

#### 
*Learning Note: What is Tinker?*

*We've taken the liberty of loading some firmware onto your device for you. It's called Tinker, and it helps you talk to your device by sending power to the pins and reading power levels from the pins. Tinker's functions include:*
* *`digitalRead` reads the input of a digital pin, such as one connected to a button or motion sensor. The input will be either HIGH (powered at 3.3 V) or LOW (not powered).*
* *`digitalWrite` sends digital output to a digital pin, such as one connected to a signal light. You can set this output to HIGH (powered at 3.3 V) or LOW (not powered).*
* *`analogRead` reads the input of an analog pin, such as one connected to a temperature sensor. The input will be between 0 and 255.*
* *`analogWrite` writes analog output to an analog pin, such as a dimmable LED. You can set this output from 0 to 255.*

*We'll go over this more later, so don't worry. For more documentation on Tinker, click [here](/guide/tinker).*
#### 

As you can see on your smartphone, the circles represent different pins on your device. If you tap on these circles, you can see the Tinker functions available for the associated pins.

We could use tinker and the smartphone app to talk to any pin on your device. If you had a buzzer, an LED, a sensor, etc., you could interact with it using Tinker on your phone. But since I know you're very eager to get started, let's use an LED already provided on your device.

The D7 pin comes already wired to a small blue LED on the face of your device. When you set the power of the D7 pin to high, this LED turns on. Let's do that now.

Tap D7 then digitalWrite in the popup. Now when you tap the D7 circle the tiny blue LED should turn off or on!

**Congratulations, you just blinked an LED over the internet, using your Particle device!**


Keep in mind that with tinker, you can communicate with any of the pins, not just with the D7 LED. You can wire things to the pins to run motors, read sensors, and much more. The real fun part comes when you write your own firmware, of course. We'll go over that in later sections.

The next lesson is on [connecting over USB](/guide/photon/connect). If you've successfully connected with your smartphone and you'd like to keep playing around with Tinker, skip ahead to learn [device modes](/guide/photon/modes) and then do some [Tinker examples](/guide/photon/tinker).

Otherwise, go to the [next section](/guide/photon/connect) to learn to connect over USB.
