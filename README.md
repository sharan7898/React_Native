# React_Native

**Overview of React Native**

* React Native lets you build mobile apps using only JavaScript.

* It uses the same design as React, letting you compose a rich mobile UI from declarative components.

* With React Native, you don't build a mobile web app, an HTML5 app, or a hybrid app; you build a real mobile app that's indistinguishable from an app built using Objective-C or Java.

* React Native uses the same fundamental UI building blocks as regular iOS and Android apps. You just put those building blocks together using JavaScript and React.

## React Native Advantages

Follow are the advantages of React Native −

* JavaScript − You can use the existing JavaScript knowledge to build native mobile apps.

* Code sharing − You can share most of your code on different platforms.

* Community − The community around React and React Native is large, and you will be able to find any answer you need.

* Cross-Platform Usage: Provide facility of "Learn once write everywhere", it works for both platform Android as well iOS devices.

* Class Performance: The code written in React Native are compiled into native code, which enables it for both operating systems as well as it functions in the same way on both the platforms.

## React Native Limitations

* Native Components − If you want to create native functionality which is not created yet, you will need to write some platform specific code.

* Improving with Time: Some features of iOS and Android are still not supported, and the community is always inventing the best practices.

* Existence is Uncertain: As the Facebook develop this framework, its presence is uncertain since it keeps all the rights to kill off the project anytime. As the popularity of React Native rises, it is unlikely to happen.

## Installation and setup

here's a step-by-step guide on how to set up your environment for developing React Native apps:

1. Install Node.js and npm

Node.js is a JavaScript runtime built on Chrome's V8 JavaScript engine, which allows developers to run JavaScript on the server-side. npm is the Node.js package manager, which is used to install and manage Node.js packages and modules.

You can download and install Node.js and npm from the official website:  

https://nodejs.org/en/download/

2.	Install Java Development Kit (JDK)

React Native requires the Java Development Kit (JDK) to be installed on your computer, as it uses Java for Android development. You can download and install the latest version of JDK from the official website:

https://www.oracle.com/java/technologies/javase-downloads.html

If you have already installed Node on your system, make sure it is Node 14 or newer. If you already have a JDK on your system, we recommend JDK11. You may encounter problems using higher JDK versions.

After installation confirm the version by opening the command terminal:

![installation1](Images/Screenshot%20(37).png)

**node –v**

**npm –v**

**java -version**

3.	Install Android Studio and Android SDK

Android Studio is the official Integrated Development Environment (IDE) for Android app development, and it comes with the Android Software Development Kit (SDK) included. You can download and install Android Studio from the official website: https://developer.android.com/studio

After installing Android Studio, you need to open it and install the Android SDK for the version of Android you want to target. You can do this by going to the "SDK Manager" in Android Studio and selecting the appropriate SDK version.

![installation2](/Images/Screenshot%20(38).png)

Click on More Actions

![installation3](/Images/Screenshot%20(39).png)

Select SDK Manager and  select the versions to apply as shown in image:

![installation4](/Images/Screenshot%20(40).png)

![installation5](/Images/Screenshot%20(41).png)

Note: After this step Edit the System Environment

Please refer the video for the complete Installation Process:
(167) React Native Environment setup for windows | 2022-23 |Windows 11 | Mr DevGeek | Muhammad Aamir Malik - YouTube

4.	Set up your development environment

To set up your development environment, Create folder in the localdisk ,you need to install the React Native command-line interface (CLI) using npm. Open a terminal or command prompt and run the following command:

**npm install -g react-native**

![installation6](/Images/Screenshot%20(44).png)

This will install the React Native CLI globally on your computer, which you can use to create and manage React Native projects.

5. Create a new React Native project

To create a new React Native project, open a terminal or command prompt and run the following command:

**react-native init demo**

![installation6](/Images/Screenshot%20(45).png)

Open The Visual Studio in the same folder(demo) and open the terminal write the following code:

**npx  react-native start**

![installation7](/Images/Screenshot%20(46).png)

Following by this command in a new terminal:

**npx react-native run-android** 

![installation8](/Images/Screenshot%20(47).png)

This will build your app and run it in the Android emulator or on a connected Android device.

![installation9](/Images/Screenshot%20(48).png)

Note:
For Complete Installation go through this video:

https://www.youtube.com/watch?v=4wT_f-ku7MQ&t=449s

Offical Website environment setup:

https://reactnative.dev/docs/environment-setup?guide=native