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

## React Native Style

There are a couple of ways to style your elements in React Native.

You can use the style property to add the styles inline. However, this is not the best practice because it can be hard to read the code.
Another way , is to use the Stylesheet for styling.

**Example 1**

In this example, we will use both inline style as well as StyleSheet.create. Inline styles are applied at where the components are created.

**App.js**

```

 import React, { Component } from 'react';  
import { AppRegistry, StyleSheet, Text, View } from 'react-native';  
export default class ImplementingStyle extends Component {  
    render() {  
        return (  
            <View>  
                <Text style={{ backgroundColor: '#a7a6a9', color: 'yellow', fontSize: 20 }}>this is inline style</Text>  
                <Text style={styles.green}>just green</Text>  
                <Text style={styles.biggray}>just biggray</Text>  
                <Text style={[styles.biggray, styles.green]}>biggray, then green</Text>  
                <Text style={[styles.green, styles.biggray]}>green, then biggray</Text>  
            </View>  
        );  
    }  
}  
const styles = StyleSheet.create({  
    biggray: {  
        color: 'gray',  
        fontWeight: 'bold',  
        fontSize: 30,  
    },  
    green: {  
        color: 'green',  
    },  
});

```

**Output:**

![Styleeaxmple1](/Images/style1.png)

#### Example 2

We can also use the external JavaScript file to style our application. In this example, we create external JS file and import it into our App.js file.

**StyleComponent.js**

```

import React, { Component } from 'react'  
import { Text, View, StyleSheet } from 'react-native' 
const StyleComponent = (props) => {  
    return (  
        <View>  
            <Text style = {styles.myState}>  
                {props.myState}  
            </Text>  
        </View>  
    )  
}  
export default StyleComponent    
const styles = StyleSheet.create ({  
    myState: {  
        marginTop: 20,  
        textAlign: 'center',  
        color: 'green',  
        fontWeight: 'bold',  
        fontSize: 20  
    }  
}) 

```

**App.js**

```

 import React from 'react';  
import { StyleSheet, Text, View } from 'react-native';  
import StyleComponent from './StyleComponent'  
  
export default class App extends React.Component {  
    state = {  
        myState: 'This is my state, style through external style'  
    }  
    render() {  
        return (  
            <View>  
                <StyleComponent myState = {this.state.myState}/>  
            </View>  
        );  
    }  
} 

```

**Output:**

![Style2](/Images/Style2.png)

## React Native FlexBox

To accommodate different screen sizes, React Native offers Flexbox support.

We will use the same code that we used in our React Native - Styling chapter. We will only change the PresentationalComponent.

Layout

To achieve the desired layout, flexbox offers three main properties − flexDirection justifyContent and alignItems.

|Property|	Values	| Description |
|---------|---------|-------------|
|flexDirection	|'column', 'row'|	Used to specify if elements will be aligned vertically or horizontally.|
|justifyContent	|'center', 'flex-start', 'flex-end', 'space-around', 'space-between'|	Used to determine how should elements be distributed inside the container.|
|alignItems	|'center', 'flex-start', 'flex-end', 'stretched' |	Used to determine how should elements be distributed inside the container along the secondary axis (opposite of flexDirection)|

If you want to align the items vertically and centralize them, then you can use the following code.


**App.js**

```

import React, { Component } from 'react'
import { View, StyleSheet } from 'react-native'
const Home = (props) => {
   return (
      <View style = {styles.container}>
         <View style = {styles.redbox} />
         <View style = {styles.bluebox} />
         <View style = {styles.blackbox} />
      </View>
   )
}
export default Home
const styles = StyleSheet.create ({
   container: {
      flexDirection: 'column',
      justifyContent: 'center',
      alignItems: 'center',
      backgroundColor: 'grey',
      height: 600
   },
   redbox: {
      width: 100,
      height: 100,
      backgroundColor: 'red'
   },
   bluebox: {
      width: 100,
      height: 100,
      backgroundColor: 'blue'
   },
   blackbox: {
      width: 100,
      height: 100,
      backgroundColor: 'black'
   },
})

```

**Output:**

![Flexbox](/Images/Flexbox.png)

#### Example:2

If the items need to be moved to the right side and spaces need to be added between them, then we can use the following code.

**App.js**

```

import React, { Component } from 'react'
import { View, StyleSheet } from 'react-native'

const App = (props) => {
   return (
      <View style = {styles.container}>
         <View style = {styles.redbox} />
         <View style = {styles.bluebox} />
         <View style = {styles.blackbox} />
      </View>
   )
}

export default App

const styles = StyleSheet.create ({
   container: {
      flexDirection: 'column',
      justifyContent: 'space-between',
      alignItems: 'flex-end',
      backgroundColor: 'grey',
      height: 600
   },
   redbox: {
      width: 100,
      height: 100,
      backgroundColor: 'red'
   },
   bluebox: {
      width: 100,
      height: 100,
      backgroundColor: 'blue'
   },
   blackbox: {
      width: 100,
      height: 100,
      backgroundColor: 'black'
   },
})

```

**Output:**

![FlexBox2](/Images/Flexbox2.png)

## React Native ListView

The ListView Component is an inbuilt React Native view component that displays a list of items in a vertically scrollable list. It requires a ListView.

DataSource API to populate a simple array of data blobs and instantiate the ListView component with a data source and a renderRow callback.

The major advantage of using the ListView Component over the ScrollView Component is that it overcomes the performance shortcomings of the ScrollView Component. 

Behind the scenes, however, the ListView Component uses a ScrollView as its scrollable component. Thus, the ListView Component is an abstraction that optimizes the ScrollView Component.

**Example:**

**App.js**

```

import React, { Component } from 'react'
import { Text, View, TouchableOpacity, StyleSheet } from 'react-native'
   
class List extends Component {
   state = {
      names: [
         {
            id: 0,
            name: 'Ben',
         },
         {
            id: 1,
            name: 'Susan',
         },
         {
            id: 2,
            name: 'Robert',
         },
         {
            id: 3,
            name: 'Mary',
         }
      ]
   }
   alertItemName = (item) => {
      alert(item.name)
   }
   render() {
      return (
         <View>
            {
               this.state.names.map((item, index) => (
                  <TouchableOpacity
                     key = {item.id}
                     style = {styles.container}
                     onPress = {() => this.alertItemName(item)}>
                     <Text style = {styles.text}>
                        {item.name}
                     </Text>
                  </TouchableOpacity>
               ))
            }
         </View>
      )
   }
}
export default List

const styles = StyleSheet.create ({
   container: {
      padding: 10,
      marginTop: 3,
      backgroundColor: '#d9f9b1',
      alignItems: 'center',
   },
   text: {
      color: '#4f603c'
   }
})

```
**OutPut:**

![ListView](/Images/Listview.png)

## React Native TextInput

In this chapter, we will show you how to work with TextInput elements in React Native.

The Home component will import and render inputs.

**App.js**

```
import React from 'react';
import Inputs from './inputs.js'

const App = () => {
   return (
      <Inputs />
   )
}
export default App;

```

Inputs

We will define the initial state.

After defining the initial state, we will create the handleEmail and the handlePassword functions. These functions are used for updating state.

The login() function will just alert the current value of the state.

We will also add some other properties to text inputs to disable auto capitalisation, remove the bottom border on Android devices and set a placeholder.

**inputs.js**

```

import React, { Component } from 'react'
import { View, Text, TouchableOpacity, TextInput, StyleSheet } from 'react-native'

class Inputs extends Component {
   state = {
      email: '',
      password: ''
   }
   handleEmail = (text) => {
      this.setState({ email: text })
   }
   handlePassword = (text) => {
      this.setState({ password: text })
   }
   login = (email, pass) => {
      alert('email: ' + email + ' password: ' + pass)
   }
   render() {
      return (
         <View style = {styles.container}>
            <TextInput style = {styles.input}
               underlineColorAndroid = "transparent"
               placeholder = "Email"
               placeholderTextColor = "#9a73ef"
               autoCapitalize = "none"
               onChangeText = {this.handleEmail}/>
            
            <TextInput style = {styles.input}
               underlineColorAndroid = "transparent"
               placeholder = "Password"
               placeholderTextColor = "#9a73ef"
               autoCapitalize = "none"
               onChangeText = {this.handlePassword}/>
            
            <TouchableOpacity
               style = {styles.submitButton}
               onPress = {
                  () => this.login(this.state.email, this.state.password)
               }>
               <Text style = {styles.submitButtonText}> Submit </Text>
            </TouchableOpacity>
         </View>
      )
   }
}
export default Inputs

const styles = StyleSheet.create({
   container: {
      paddingTop: 23
   },
   input: {
      margin: 15,
      height: 40,
      borderColor: '#7a42f4',
      borderWidth: 1
   },
   submitButton: {
      backgroundColor: '#7a42f4',
      padding: 10,
      margin: 15,
      height: 40,
   },
   submitButtonText:{
      color: 'white'
   }
})

```

Whenever we type in one of the input fields, the state will be updated. When we click on the Submit button, text from inputs will be shown inside the dialog box.

**OutPut:**

![TextInput](/Images/TextInput.png)

![TextInput2](/Images/Textinput2.png)

Whenever we type in one of the input fields, the state will be updated. When we click on the Submit button, text from inputs will be shown inside the dialog box.

![TextInput3](/Images/Textinput3.png)

## React Native ScrollView

The ScrollView is a generic scrollable container, which scrolls multiple child components and views inside it. 

In the ScrollView, we can scroll the components in both direction vertically and horizontally. By default, the ScrollView container scrolls its components and views in vertical. 

To scroll its components in horizontal, it uses the props horizontal: true (default, horizontal: false).

**React Native ScrollView Example**

In this example, we create a vertical ScrollView using Text and Button components.

**App.js**

```

import React, { Component } from 'react';  
import { AppRegistry, ScrollView, Image, Text, Button, StyleSheet } from 'react-native';  
  
export default class ScrolledViewExample extends Component {  
    onPressButton() {  
        alert('You clicked the button!')  
    }  
  
    render() {  
        return (  
            <ScrollView >  
                <Text style={{fontSize:20}}>Scroll me plz</Text>  
                <Button title={'Button 1'} onPress={this.onPressButton} />  
                <Text style={{fontSize:20}}>React Native Example of ScrollView</Text>  
                <Button title={'Button 2'} onPress={this.onPressButton}/>  
                <Text style={{fontSize:20}}>React Native ScrollView Example</Text>  
                <Button title={'Button 3'} onPress={this.onPressButton}/>  
                <Text style={{fontSize:20}}>If you like</Text>  
                <Button title={'Button 4'} onPress={this.onPressButton}/>  
                <Text style={{fontSize:20}}>Scrolling down</Text>  
                <Button title={'Button 5'} onPress={this.onPressButton}/>  
                <Text style={{fontSize:20}}>Scrolling down</Text>  
                <Button title={'Button 6'} onPress={this.onPressButton}/>  
                <Text style={{fontSize:20}}>What's the best</Text>  
                <Button title={'Button 7'} onPress={this.onPressButton}/>  
                <Text style={{fontSize:20}}>What's the best</Text>  
                <Button title={'Button 8'} onPress={this.onPressButton}/>  
                <Text style={{fontSize:20}}>Framework around?</Text>  
                <Button title={'Button 9'} onPress={this.onPressButton}/>  
                <Text style={{fontSize:20}}>Framework around?</Text>  
                <Button title={'Button 10'} onPress={this.onPressButton}/>  
                <Text style={{fontSize:20}}>React Native</Text>  
                <Button title={'Button 11'} onPress={this.onPressButton}/>  
                <Text style={{fontSize:20}}>Scroll me plz</Text>  
                <Button title={'Button 12'} onPress={this.onPressButton} />  
                <Text style={{fontSize:20}}>Scroll me plz</Text>  
                <Button title={'Button 13'} onPress={this.onPressButton}/>  
                <Text style={{fontSize:20}}>If you like</Text>  
                <Button title={'Button 14'} onPress={this.onPressButton}/>  
                <Text style={{fontSize:20}}>If you like</Text>  
                <Button title={'Button 15'} onPress={this.onPressButton}/>  
                <Text style={{fontSize:20}}>Scrolling down</Text>  
                <Button title={'Button 16'} onPress={this.onPressButton}/>  
            </ScrollView>  
        );  
    }  
}  
// skip this line if you are using Create React Native App  
AppRegistry.registerComponent('AwesomeProject', () => ScrolledViewExample);

```

**OutPut:**

![ScrollViewVertical](/Images/ScrollView.png)

#### Horizontal Example

**React Native Horizontal ScrollView Example**

The horizontal ScrollView scrolls the components and views from left to right. It will be implemented by setting the props horizontal to true (horizontal={true}).

**App.js**


```
import React, { Component } from 'react';  
import { AppRegistry, ScrollView, View, Image, Text, Button, StyleSheet } from 'react-native';  
  
export default class ScrolledViewExample extends Component {  
    onPressButton() {  
        alert('You clicked the button!')  
    }  
    render() {  
        return (  
            <ScrollView  horizontal={true} style={styles.container}>  
                <Text style={{fontSize:22, padding: 10}}>Horizontal ScrollView</Text>  
                <View style={[{ width: 220,height: 70,padding: 10 }]}>  
                    <Button  
                        onPress={this.onPressButton}  
                        title="Button 1"  
                        color="#FF3D00"  
                    />  
                </View>  
                <Text style={{fontSize:22, padding: 10}}>javatpoint</Text>  
                <View style={[{ width: 220,height: 70,padding: 10 }]}>  
                    <Button  
                        onPress={this.onPressButton}  
                        title="Button 2"  
                        color="#3D00FF"  
                    />  
                </View>  
                <Text style={{fontSize:22, padding: 10}}>React Native ScrollView Example</Text>  
                <View style={[{ width: 220,height: 70,padding: 10 }]}>  
                    <Button  
                        onPress={this.onPressButton}  
                        title="Button 3"  
                        color="#FFFF3D"  
                    />  
                </View>  
                <Text style={{fontSize:22, padding: 10}}>If you like</Text>  
                <View style={[{ width: 220,height: 70,padding: 10 }]}>  
                    <Button  
                        onPress={this.onPressButton}  
                        title="Button 4"  
                        color="#FF3DFF"  
                    />  
                </View>  
                <Text style={{fontSize:22, padding: 10}}>Scrolling horizontal</Text>  
                <View style={[{ width: 220,height: 70,padding: 10 }]}>  
                    <Button  
                        onPress={this.onPressButton}  
                        title="Button 5"  
                        color="#3DFF00"  
                    />  
                </View>  
            </ScrollView>  
        );  
    }  
}  
const styles = StyleSheet.create({  
    container:{  
        flex: 1,  
    },  
/*    buttonStyle:{ 
        height: 50, 
        width: 70, 
    }*/  
})  
// skip this line if you are using Create React Native App  
AppRegistry.registerComponent('AwesomeProject', () => ScrolledViewExample);

```

**OutPut:**

![ScrollviewHorizontal](/Images/ScrollviewH.png)

## React Native Button

Most users interact with mobile through touches. There are combinations of gestures that work on it, such as tapping on the button, zooming the map, scrolling a list, etc. A button is one of the components that work on its click.

React Native Button is a basic component that works by clicking on it. It imports the Button class of react-native.

**React Native Button Example**

In this example, we will work on the button component. React Native Button component imports the Button class of react-native library. It has several props such as title, onPress, accessibilityLabel, etc. which are mentioned above.

In the previous article Positioning Element with Flex, we learned how to position elements in View.

In the below code the title prop sets the title of a button, onPress prop calls the mention function and performs an event. The color prop sets the color of the button, and disabled={true} makes the button to disable.

**App.js**

```

import React, { Component } from 'react';  
import { Alert, AppRegistry, Button, StyleSheet, View } from 'react-native';  
  
export default class ButtonBasics extends Component {  
    onPressButton() {  
        Alert.alert('You clicked the button!')  
    }  
  
    render() {  
        return (  
            <View style={styles.container}>  
                <View style={styles.buttonContainer}>  
                    <Button  
                        onPress={this.onPressButton}  
                        title="Press Me"  
                    />  
                </View>  
                <View style={styles.buttonContainer}>  
                    <Button  
                        onPress={this.onPressButton}  
                        title="Press Me"  
                        color="#009933"  
                    />  
                </View>  
                <View style={styles.multiButtonContainer}>  
                    <Button  
                        onPress={this.onPressButton}  
                        title="A disabled button"  
                        disabled={true}  
                    />  
                    <Button  
                        onPress={this.onPressButton}  
                        title="OK!"  
                        color="#009933"  
                    />  
                </View>  
            </View>  
        );  
    }  
}  
  
const styles = StyleSheet.create({  
    container: {  
        flex: 1,  
        justifyContent: 'center',  
    },  
    buttonContainer: {  
        margin: 20  
    },  
    multiButtonContainer: {  
        margin: 20,  
        flexDirection: 'row',  
        justifyContent: 'space-between'  
    }  
})

```
**OutPut:**

![button](/Images/button.png)

![button1](/Images/button1.png)

## React Native Animation

React Native has an Animated API that handles animations in the app. It has various functions to create most types of animation(E.g Fading, color change, width and Height change, position change). We will mostly be using Animated.parallel, Animated.timing, Animated.value, and Animated.View this example.

**Steps to Create Animation:**

1.Defining State: We will import Animated from ‘react-native’.Then we will declare our state that will be later changed by the animate function. In this, we are using “right” which will shift the <Animated.View> from left-to-right and vice-versa. And “radius” state which will change borderRadius of the View during animation.

2.Defining Animation functions: We will define two functions leftToRight and rightToLeft which will animate the View when called. In this, we are using Animated.parallel() function which is used to run multiple animations simultaneously. And Animated.timing() function which takes state, duration of the animation, final value as parameter. The Start() for starting the animation.

3.Creating the View: Now we will create a View using <Animated.View> and in style pass the animation state.

Note: Use <Animated.View> for creating a View that will animate based on animated state.Normal <View> will throw Stack limit exceeded error.

#### Example 1

**App.js**

```

import React, { Component } from 'react';
import { Text, View, Animated, Dimensions, Button } from 'react-native';

class App extends Component {
constructor(props) {
	super(props);
	this.state = {
	right: new Animated.Value(
		Dimensions.get('window').width - 200),
	radius: new Animated.Value(0),
	};
}
leftToRight = () => {
	Animated.parallel([
	Animated.timing(this.state.radius, {
		toValue: 200,
		duration: 1000,
		useNativeDriver: false,
	}),
	Animated.timing(this.state.right, {
		toValue: 0,
		duration: 1000,
		useNativeDriver: false,
	}),
	]).start();
};
rightToLeft = () => {
	Animated.parallel([
	Animated.timing(this.state.radius, {
		toValue: 0,
		duration: 1000,
		useNativeDriver: false,
	}),
	Animated.timing(this.state.right, {
		toValue: Dimensions.get('window').width - 200,
		duration: 1000,
		useNativeDriver: false,
	}),
	]).start();
};

render() {
	return (
	<View style={{ flex: 1 }}>
<Animated.View
		style={{
marginTop: '30%',
			backgroundColor: 'red',
			height: 200,
			width: 200,
			right: this.state.right,
			position: 'absolute',
			justifyContent: 'center',
			borderRadius: this.state.radius,
		}}>
<Text
			style={{
			textAlign: 'center',
			color: 'white',
			}}>
			Animated View
		</Text>
		</Animated.View>
		<View
style={{
			position: 'absolute',
			bottom: 0,
			width: '100%',
			height: '20%',
			justifyContent: 'space-evenly',
		}}>
Button title="Left to right"
onPress={() => this.leftToRight()} />
<Button title="right to left"
			onPress={() => this.rightToLeft()} />

  );    
}
}

export default App;


```


**OutPut:**

![Animated](/Images/Animated1.png)

![Animated2](/Images/Animated2.png)

#### Example 2

**Interpolation:** Let’s suppose we want to use “%” instead of a number for defining our right style property.If we pass “%” as in <Animated.View> and try to change it in our Animated.timing() function we will get an error. This is where interpolation helps.It maps input ranges to output ranges(E.g. 0-100 into 0%-100%).We just have to apply interpolation in <Animated.View> right style prop and the rest of the code will be the same.

**Example:**

**App.js**

```
<Animated.View
style={{
	marginTop: '30%',
	backgroundColor: 'red',
	height: 200,
	width: 200,
	right: this.state.right.interpolate({
	inputRange: [0, 100],
	outputRange: ['0%', '100%'],
	}),
	position: 'absolute',
	justifyContent: 'center',
	borderRadius: this.state.radius,
}}>
<Text
	style={{
	textAlign: 'center',
	color: 'white',
	}}>
	Animated View
</Text>
</Animated.View>

```