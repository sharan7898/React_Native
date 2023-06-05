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

![installation3](/React_Native.code-workspaceImages/Screenshot%20(39).png)

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

## React Native State

In React Native, for data that is going to change, we have to use state. You can think of it as a variable. It allows us to store data and also change it when we want.

Whenever you define a state, you need to provide an initial value for it. After that, you can use setState function provided by React Native to change it whenever you want. Whenever setState is called and state changes, it will re-render the component in which it’s being used.

To use state, you need to import useState from “react”.

**Example 1**: Open App.js file and write the below code in that file.

Note: We will create a state called message. We will provide an empty string as the initial value for this state. There will be one TextInput which allows user to insert any text message. We will save this text string in message state using setMessage function. And when user hit the submit button on keyboard, an alert will show with the message.

**App.js**

**Code**:

```

import { StyleSheet, SafeAreaView, Text, TextInput } from "react-native";
import { useState } from "react";
export default function App() {
	const [message, setMessage] = useState("");
	return (
		<SafeAreaView style={styles.container}>
			<TextInput
				placeholder="Enter message here"
				value={message}
				onChangeText={(text) => setMessage(text)}
				style={styles.input}
				onSubmitEditing={() => alert(message)}
			/>
		</SafeAreaView>
	);
}
const styles = StyleSheet.create({
	container: {
		flex: 1,
		backgroundColor: "#fff",
		alignItems: "center",
		justifyContent: "center",
	},
	input: {
		fontSize: 20,
		color: "#228B22",
		fontWeight: "bold"
	},
});

```

**OutPut:**

![stateExample](/Images/state%20ex.png)

#### Example 2:

Let's create another example of state data in which we interchange the Text value "Show" and "Hide" to show and hide the input password.

Create three state variables that will be changed by clicking the Text component defined as a state. Clicking the Text component calls the handleToggle function, and the current state of Boolean variable "isPasswordVisible" is assigned in it. Here, if the condition checks the value of "isPasswordVisible" and proceeds accordingly.

**App.js**

**Code:**

```

import React, { Component } from 'react';  
import {StyleSheet,Text,View,TextInput,TouchableOpacity} from 'react-native';  
  
export default class App extends Component {  
    state: {  
        password: string,  
        isPasswordVisible: boolean,  
        toggleText: string,  
    }  
    constructor(props: Props) {  
        super(props);  
        this.state = {  
            password: '',  
            isPasswordVisible: true,  
            toggleText: 'Show',  
        };  
    }  
    handleToggle = () => {  
        const { isPasswordVisible } = this.state;  
        if (isPasswordVisible) {  
            this.setState({ isPasswordVisible: false });  
            this.setState({ toggleText: 'Hide' });  
        } else {  
            this.setState({ isPasswordVisible: true });  
            this.setState({ toggleText: 'Show' });  
        }  
    };  
    render() {  
        return (  
            <View style={styles.container}>  
                <TextInput  
                    secureTextEntry={this.state.isPasswordVisible}  
                    style={{ width: 400, height: 50, backgroundColor: '#a7a6a9', color: 'white', fontSize: 20 }}  
                />  
                <TouchableOpacity onPress={this.handleToggle}>  
                    <Text  style={{fontSize: 20}}>{this.state.toggleText}</Text>  
                </TouchableOpacity>  
            </View>  
        );  
    }  
}  
const styles = StyleSheet.create({  
    container: {  
        flex: 1,  
        justifyContent: 'center',  
        alignItems: 'center',  
    }  
});

```

**OutPut:**

![stateexample2](/Images/state%20ex1%20(1).png)

![stateexample3](/Images/state%20ex1%20(2).png)

## React Native Props

The properties of React Native components are simply pronounced as props. In React Native, most of the components can be customized at the time of their creation with different parameters. These parameters are known as props. They are immutable, and they cannot be changed.

One of the examples of props is a source property if Image component which controls the image is displayed over the device screen.

**App.js**

**Example:**

```

import React, { Component } from 'react';  
import {  
  Platform,  
  StyleSheet,  
  Image,  
  Text,  
  View  
} from 'react-native';  
export default class App extends Component<{}> {  
  render() {  
    let imagePath = { uri: 'https://facebook.github.io/react-native/img/header_logo.png'};  
    return (  
        <View style={styles.container}>  
          <Text style={styles.welcome}>Welcome to React Native!</Text>  
          <Image source={imagePath} style={{width: 250, height: 250}} />  
        </View>  
    );  
  }  
}  
const styles = StyleSheet.create({  
  container: {  
    flex: 1,  
    justifyContent: 'center',  
    alignItems: 'center',  
    backgroundColor: '#a7a6a9',  
  },  
  welcome: {  
    fontSize: 30,  
    textAlign: 'center',  
    margin: 20,  
  }  
}); 

```

**Output:**

![props-example](/Images/Screenshot%20(56).png)

#### Using props in our own Component

We can also use props in our components. A single component can be used in many different places in the app by making slightly different properties in each place. To implement the props in our component, this.props is applied followed by the property.

For example, one of the basic React Native components is Text. When we create a Text component, we can use a prop "name" as props to control its appearance. We also apply the StyleSheet to the component which is used as our component.

**App.js**

**Example:**

```
 import React, { Component } from 'react';  
import { StyleSheet, Text, View } from 'react-native'; 
class ChildClass extends Component {  
  render() {  
    return (  
        <View style={{alignItems: 'center'}}>  
          <Text style={styles.welcome}>Hello {this.props.name}!</Text>  
        </View>  
    );  
  }  
} 
export default class ParentsClass extends Component {  
  render() {  
    return (  
        <View style={{alignItems: 'center'}}>  
          <ChildClass name='Ashu' />  
          <ChildClass name='Aman' />  
          <ChildClass name='Max' />  
        </View>  
    );  
  }  
}  
const styles = StyleSheet.create({  
   welcome: {  
    fontSize: 30,  
  }  
});  

```

**Output:**

![propsexample2](/Images/Screenshot%20(57).png)