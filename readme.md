# React Native

**Step 1:**

Install Node.js (LTS version)

**Step 2:**

Run following command in CLI/Terminal, -g means globally.
```
npm install -g expo-cli
```
**Step 3:**

Switch to the folder where you want to make you React Native project.

![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/001.png)

**Step 4:**

Make a project by following command.
```
expo init FirstReactApp
```
**Step 5:**

Download VS-code.

**Step 6:**

Select project folder of react app in VS-code.

**Step 7:**

Download Expo Go app on mobile, in there you can preview your app.

**Step 8:**

Open terminal in VS-code and run following command.
```
npm start
```
keep this “npm start” process up and running as long as you are working on your code.

**Step 9:**

Scan the QR-code in the terminal with the expo go app.

Ctrl + s for hot reload.

Till this point you can run you app and go along, following steps are for creating android simulator.

**Step 10:**

Download android studio.

**Step 11:**

Open android studio and go to virtual device manager.

**Step 12:**

Create device, pick a device with google play icon.

**Step 13:**

Click play button to lunch emulator.

**Step 14:**
```
npm start
```
then press shft + “a” to lunch app on emulator.

# <a name="_toc12570"></a>**Folder Structure**
**Assets** – store resources like images

**Package.json** – list all the dependencies, scripts command are those commands which we can run through npm

**App.json** – here we can configure some setting and behavior of app. This is a file which will be picked up by expo when our app is built for preview or for actual app store. We can set app name, version etc.

**App.js** – Code file


# <a name="_toc17487"></a>**Core Components**
**Core components** are ready-to-use components available from React Native, which include 
```
<View>, <Text>, <Image>, <ScrollView>, <Button>, and <TextInput>.
```
## <a name="_toc360"></a>Importing Core Components
You can import core components into your Expo project from the react-native package.
```
import { View, Text } from 'react-native';
```

## <a name="_toc30626"></a>Core Components Optional Functionality
Core components may have more optional functionality, which you can configure through the props.
```
function App() {
  return (
    {\* Text components can be with `numberofLines` prop */}
    <Text numberOfLines={1}>
      quam elementum pulvinar etiam non quam lacus suspendisse faucibus interdum posuere lorem ipsum dolor sit
    </Text>
  );

}
```

## <a name="_toc5970"></a><View> 
The `<View>` component is a generic “visible” container without any semantic meaning or noticeable performance impact, best translated as `<div>` from web. 

That’s right, `<View>` acts very similar to `<div>`, and the basic idea is that it is a container perfect for dividing up and styling your page.

- Hold and layout other components.
- Multiple child component in it
- There can be nested <View>

## <a name="_toc20568"></a>`<ScrollView>` 
The `<ScrollView>` component is a generic “visible” container with scrolling, but it’s less performant than <View>, making it less suitable for simple styling and short lines of text.

## <a name="_toc16244"></a>`<Text>` 
`<Text></Text>` is a wrapper for any text in your page. This component is similar to a `<p>` tag in HTML. 

## <a name="_toc15428"></a>`<Image>` 
The `<Image>` component is an optimized way to render images from various sources, including remote HTTP access, local assets imported with require, and base64 encoded strings.
```
<Image source={require('./local/asset.jpg')} />
```
```
<Image source={{ uri: 'https://docs.expo.io/static/images/header/sdk.svg' }} />
```
```
<Image source={{ uri: 'data:image/png;base64,<base64-string>=' }} />
```

## <a name="_toc23895"></a>`<TextInput>` 
The `<TextInput>` component can capture alphanumeric input from the user. Its behavior can be modified with the onChangeText prop, which accepts a function.
```
const [input, setInput] = useState('');
// example use of input
console.log(input);  

return (
  <TextInput
    placeholder="What is your name?"
    onChangeText={setInput}
  />

);
```
# <a name="_toc4552"></a>**Styling React Native App**
To apply style, we use **style** prop, we can define style inline and also in stylesheet object.

And in style prop we passed JavaScript object. 

You can add styling to your component using style props you simply add style props to your element it accepts an object of properties.

🔑 Remember: Button does not have style prop.


## <a name="_toc21222"></a>Styling Inline
```
<Text style= {{margin: 18, borderWidth: 2, borderColor: "red", padding: 8}}>Hello world</Text> 
<Text style= {{}}>Welcome</Text>
```
🔑  {{double bracket when using inline styling}}


## <a name="_toc17387"></a>Stylesheet object
🔑 Recommended way as we can re-use the styles.
```
export default function App() {

  return (
    <View style={styles.container}>
      <Text style= {styles.primaryHeading}>Hello world</Text> 
      <Text style={styles.primaryHeading}>Welcome</Text>
    </View>
  );
}

const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#fff',
    alignItems: 'center',
    justifyContent: 'center',

  },

  primaryHeading:{
    margin: 18,
    borderWidth: 5,
    borderColor: "red",
    padding: 8
  }
});

```
# <a name="_toc9390"></a>**Flexbox**
Layouts are typically created with flexbox, Very Similar to browser CSS flexbox! Elements are positioned inside of containers.

Flexbox is enable on all the view, you start using flex properties right away.

![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/002.png)

Properties: Flexbox Layout in React Native

![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/003.png)
## <a name="_toc13344"></a>Two Axes of Flexbox
Flexbox deals with two axes –

- **Main Axis:** It is defined by property flex-direction.
- **Cross Axis:** It runs perpendicular to the main axis.

<a name="_toc18696"></a>**Flex Container**

The area of the document on which we want to apply the flex property can be said as a flex container. To create a flex container, you just need to set the display property(of the area’s container) as flex or inline-flex. And items within the area’s container will become flex items.
## <a name="_toc30534"></a>flexDirection
```
‘column’/’column-reverse’/’row’/’row-reverse’
```
Defines the direction of the main axis. Opposite to the web, React Native default flexDirection is column which makes sense, most mobile apps much more vertically oriented.

![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/004.png)

## <a name="_toc16792"></a>flex
flex will define how your items are going to “fight” over the available space along your **primary axis**. Most of the time you will want your app container to be flex:1 to take all of the screen height. Space will be divided according to each element flex property. In the following example the red, yellow and the green views are all children in the container view that got flex:1. The red view got flex:1 , the yellow view got flex:2 and the green view got flex:3 . 1+2+3=6 which means that red view will get 1/6 of the space, the yellow 2/6 of the space and the green 3/6 of the space. 

![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/005.png)
## <a name="_toc20394"></a>justifyContent
```
‘flex-start’,’flex-end’,’center’,’space-between’,’space-around’
```
Determines the **distribution** of children along the **primary axis**. 

![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/006.png)

The default value is flex-start
## <a name="_toc22988"></a>alignItems
```
‘flex-start’, ‘flex-end’, ‘center’, ‘stretch’
```
Align items along the **cross axis**. So in a default view(column), it will control the horizontal alignment of items.

![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/007.png)

- stretch wouldn’t work if you have a specific width
- If you don’t have a specific width flex-start and flex-end wouldn’t understand what to do…
## <a name="_toc27664"></a>alignSelf
```
‘flex-start’, ‘flex-end’, ‘center’, ‘stretch’
```
align an **item** along the **cross axis** overwriting his **parent** alignItem property

![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/008.png)

## <a name="_toc31290"></a>flexWrap
```
‘wrap’, ‘nowrap’
```
Controls whether flex items are forced on a single line or can be wrapped on multiple lines.

![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/009.png)

The default value is nowrap
## <a name="_toc15373"></a>alignContent
```
‘flex-start’,’center’,’flex-end’,’stretch’,’space-between’,’space-around’
```
So, if you went with flexWrap:'wrap' you have multiple lines of items, this property will help you align the lines on the cross-axis.

![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/010.png)

## <a name="_toc16400"></a>position
```
‘relative’,’absolute’
```
In React Native, everything is **relative** by default.

Think of your container as a line of people. And you are telling each person to stand 5 meters behind the person in front of him (marginTop: 5). If this person is set to relative he will respect the line and will position himself relatively to the person in front of him. If this person is set to absolute he will ignore all of the people in the line and will position himself as if the line was empty, 5 meters from where the line (his parent container) starts.

position in React Native is similar to regular CSS, but everything is set to relative by default, so absolute positioning is always relative to the parent.

If you want to position a child using specific numbers of logical pixels relative to its parent, set the child to have absolute position.

![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/011.png)
## <a name="_toc27711"></a>zIndex
You can control which components display on top of others. In the following example the zIndex of the yellow square to 1.

![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/012.png)
## <a name="_toc16634"></a> 🔑 Key things:
- If you don’t specify the width and height of the container, then it will take the width and height as much as it’s child required.

- But if a view (Parent View) have some height and width then it child views will inherit the height of the parent means it will be as tall as its parent(“stretch”) and width have no effect means it take as much width as it’s child required.

- Justify-content to organize element along main axis.

- And align-item to organize element along cross axis.

# <a name="_toc28959"></a>**Get TextInput value.**
```
export default function App() {
  function goalInputController(enteredText) {
    console.log(enteredText)
  };

  return (
    <View style={styless.aapContainer}>
      <View style={styless.inputContainer}>
        <TextInput
          style={styless.textInput}
          placeholder='Your course gools! '
          onChangeText={goalInputController}
        />
        <Button title='Add Goal' />
      </View>
      <View style={styless.goalsContainer}>
        <Text>List of goals</Text>
      </View>
    </View>
  );
}
```
# <a name="_toc26400"></a>**UseState**
**Hooks** are a new addition in React 16.8. They let you use state and other React features without writing a class. It mainly uses to handle the state and side effects in react functional component. React Hooks are a way to use stateful functions inside a functional component. Hooks don’t work inside classes — they let you use React without classes React provides a few built-in Hooks like **useState*** and **useEffect**.

The **useState** hook lets us "remember" a value within a component function.

**The useState hook takes a single argument, our initial state, and returns an array containing two elements:**

- state - the current state
- setState - a function to update our state. i.e., **setState(newValue)**
```
const [state, setState] = useState(initialValue)
```
![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/013.png)

![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/014.png)

**selectedRoom** is the state and it is read only, and to change selectedRoom value we use **setSelectedRoom** function and pass in the new value

## <a name="_toc32127"></a>Rules of Hooks
- Only Call Hooks at the Top Level
- Don’t call Hooks inside loops, conditions, or nested functions. Instead, always use Hooks at the top level of your React function. By following this rule, you ensure that Hooks are called in the same order each time a component renders. That’s what allows React to correctly preserve the state of Hooks between multiple useState and useEffect calls. (If you’re curious, we’ll explain this in depth below.)
- Only Call Hooks from React Functions
- Don’t call Hooks from regular JavaScript functions. Instead, you can:
- Call Hooks from React function components.

# <a name="_toc28204"></a>**Get TextInput value on button click.**
```
export default function App() {
  // Declare new state variable*
  const [enteredGoalText, setenteredGoalText] = useState("")
  function goalInputController(*enteredText*) {
    setenteredGoalText(enteredText);
  };
  function onGoalButtonPressed() {
    console.log(enteredGoalText);
  }
  return (

    <View style={styless.aapContainer}>
      <View style={styless.inputContainer}>
        <TextInput
          style={styless.textInput}
          placeholder='Your course gools! '
          onChangeText={goalInputController}
        />
        <Button title='Add Goal' 
        onPress={onGoalButtonPressed} 
        />
      </View>
      <View style={styless.goalsContainer}>
        <Text>List of goals</Text>
      </View>
    </View>
  );
}
```
## <a name="_toc27130"></a>Update the list with the value of TextField on press of button.
```
export default function App() {
  // Declare new state variable
  const [enteredGoalText, setenteredGoalText] = useState("");
  const [myGoalsList, setmyGoalsList] = useState([]);
  function goalInputController(enteredText) {
    setenteredGoalText(enteredText);
  };
  function onGoalButtonPressed() {
    //setmyGoalsList([...myGoalsList, enteredGoalText]);
    // OR recommended way
    setmyGoalsList((myGoalsList) => [...myGoalsList, enteredGoalText,]);
  }
  return (
    <View style={styless.aapContainer}>
      <View style={styless.inputContainer}>
        <TextInput
          style={styless.textInput}
`          placeholder='Your course gools!
          onChangeText*={goalInputController}
        />
        <Button title='Add Goal' 
        onPress={onGoalButtonPressed} 
        />
      </View>
      <View style={styless.goalsContainer}>
        {myGoalsList.map((item)=>
          <Text style={styless.goalItem} key={item}>{item}</Text>
        )}
      </View>
    </View>
  );
}
```


## <a name="_toc4477"></a>Map through list
```
 <View style={styless.goalsContainer}>
        {myGoalsList.map((item)=>
          <Text style={styless.goalItem} key={item}>{item}</Text>
        )}
```
# <a name="_toc31966"></a>**ScrollView**
The **ScrollView** is a generic scrollable container, which scrolls multiple child components and views inside it. In the ScrollView, we can scroll the components in both directions **vertically** and **horizontally.** By default, the ScrollView container scrolls its components and views in vertical. To scroll its components in horizontal, it uses the props **horizontal: true** (default, horizontal: false).
```
import {  ScrollView  } from 'react-native';  
```
```
      <View style={styless.goalsContainer}>
        <ScrollView>
          {myGoalsList.map((item) => (
            <View style={styless.goalItem} key={item}>
              <Text style={styless.goalText} >{item}</Text>
            </View>
          ))}
        </ScrollView>
      </View>
```
There are many props which we can set on ScrollView like bouncing effect, scroll vertically etc.

The scrollview is best when we have small amount of item in the list or article type paragraphs but one down side of a scroolview is that it render all the items that are inside of it but what if we have 1000 of items, so to load/render them all in once is not a good thing. It will also build those items which are currently not visible on screen. So it will create performance issue.

So, to handle this problem we use another core component **FlatList.**

# <a name="_toc15598"></a>**FlatList**
The **FlatList** component displays the similar structured data in a **scrollable** list. It works well for large lists of data where the number of list items might change over time. The FlatList shows only those renders elements which are currently displaying on the screen, not all the elements of the list at once.

The FlatList component takes two required props: **data** and **renderItem**.

The **data** is the source of elements for the list, and **renderItem** takes one item from the source and returns a formatted component to render.

To implement the FlatList component, we need to import **FlatList** from **'react-native'** library.
```
        <FlatList
          data={myGoalsList}
          renderItem={(itemData) => {
            //itemData.index, itemData will be pass by React
            //itemData.item 
            return (
              <View style={styless.goalItem}>
                <Text style={styless.goalText} >{itemData.item}</Text>
              </View>
            )
          }}
        />
```

Now we have to pass key, so one of the best ways to pass object in the list with “key” property.
```
function onGoalButtonPressed() {
    setmyGoalsList((myGoalsList) => [...myGoalsList, {text: enteredGoalText, key: Math.random().toString()},]);
  }
```
Now flatList will automatically look for “key”, it will only look for “key” not to another name property.

But if we change **key** property name to **id** then you have to tell the FlatList by giving **KeyExtractor** property.
```
function onGoalButtonPressed() {
    setmyGoalsList((myGoalsList) => [...myGoalsList, {text: enteredGoalText, id: Math.random().toString()},]);
}
```
Now we have to tell FlatList that unique key name is now **id**,
```
        <FlatList
          data={myGoalsList}
          renderItem={(itemData) => {
            //itemData.index, itemData will be pass by React
            //itemData.item 
            return (
              <View style={styless.goalItem}>
                <Text style={styless.goalText} >{itemData.item.text}</Text>
              </View>
            )
          }}
          keyExtractor={(item, index)=>{
            return item.id;
          }}
        />
```
# <a name="_toc15954"></a>**Dividing app in components**
Make a components folder in root of project.

Now you can make .js file in it.

![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/015.png)
```
import { StyleSheet } from "react-native";
function GoalItem(){
    return <View style={styles.goalItem}>
    <Text style={styles.goalText} >{itemData.item.text}</Text>
  </View>
};

export default GoalItem;

const styles = StyleSheet.create({
    goalItem: {
        margin: 8,
        padding: 8,
        borderRadius: 6,
        backgroundColor: "#5e0acc",
    
      },
      goalText: {
        color: "white",
      }
});
```

Import to file in which they are used.
```
import GoalItem from './components/GoalItem';
```
use in the place to use
```
return <GoalItem />
```
## <a name="_toc23773"></a>pass the data:
**In child**

```
function GoalItem(props){
    return <View style={styles.goalItem}>
    <Text style={styles.goalText} >{props.text}</Text>
  </View>
};
```

**In parent**
```
return <GoalItem text = {itemData.item.text}/>
```
# <a name="_toc8905"></a>**Pressable**
It is basically a wrapper that detects touch interactions. It is a well-defined component and can be used instead of touchable components such as TouchableOpacity, Button, etc.

```
<Pressable onPress={onPressFunction}>
  <Text>Press Me</Text>
</Pressable>
```

# <a name="_toc3920"></a>**checking**
```
{modelIsVisible && <View>...</View>}
```
This means if modelIsVisible == true then render the next element otherwise if it is false don’t render it.
# <a name="_toc26118"></a>**Adding Image**
Create a Images folder inside an assets folder and drop the images in this folder

![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/016.png)
```
<Image source={require("../assets/Images/iconImg.png")} />
```
You can give style prop to image.
```
<Image style={style.image} source={require("../assets/Images/iconImg.png")} />
```
In styling

```
const style = StyleSheet.create({
    image: {
        width: 100,
        height: 100,
        margin: 15
    }
});
```
# <a name="_toc18290"></a>**Add background color to whole app.**
Go to app.json and add background property their.
```
"backgroundColor": "#1e085a",
```
# <a name="_toc823"></a>**Change Status bar color.**
Import
```
import { StatusBar } from 'expo-status-bar';
```
in root means App.js
```
return (
    <>
    <StatusBar style='light'/ >
    <View style={styless.aapContainer}>
      .
      .
      .
    </View>
    </>
  );
```


# <a name="_toc15801"></a>**React Native inbuild Icons.**
![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/017.png)

Bunch of icons libraries to import.
```
import{FontAwesome} from "@expo/vector-icons"
```

```
<View>
            <FontAwesome name='search' size={25}/>
            <TextInput 
            placeholder='Restaurants, food' 
            />
        </View>
```

# <a name="_toc23284"></a>**Shadow** 
```
const styles = StyleSheet.create({
    TextInputContainer:{
        marginTop:5,
        flexDirection:"row",
        backgroundColor:"white",
        shadowColor:"black",
        shadowOffset: {width:5, height:5},
        elevation:3,
        shadowOpacity: 1
        
    }
});
```

## <a name="_toc6767"></a>TextInput style
```
TextInputContainer:{
        marginTop:5,
        flexDirection:"row",
        backgroundColor:"white",
        shadowColor:"black",
        shadowOffset: {width:5, height:5},
        elevation:3,
        shadowOpacity: 1,
        padding:15,
        borderRadius:40
    }
```
# <a name="_toc24100"></a>**Common Style in one file and applying to multiple component.**
Create a common directory and in it create styles.js

![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/018.png)

In styles.js

```
export const elevation = {
    shadowColor: "black",
    shadowOffset: { width: 5, height: 5 },
    elevation: 3,
    shadowOpacity: 1,
}
```

Now we have to import them.
```
import {elevation} from "../common/styles"
```
now add this imported elevation in StyleSheet.create object
```
const styles = StyleSheet.create({
    TextInputContainer:{
        marginTop:5,
        borderRadius:40
    },
    elevation,
    input:{
        fontSize:20,
        marginLeft:10
    }
});
```

Apply to Components.
```
        <View style={[styles.TextInputContainer, styles.elevation]}>
            <FontAwesome name='search' size={25}/>
            <TextInput 
            style={styles.input}
            placeholder='Restaurants, food' 
            />
        </View>
```


We can also apply array of styles to component.
# <a name="_toc30086"></a>**AlignItem**
alignItems property is used to determine how should children’s components be aligned along the **secondary axis** of their container. The secondary axis is always opposite to the primary axis. If the **primary axis is a column**, then the **secondary will be a row**, and vice-versa.

**Syntax:**  
```
alignItems: stretch|center|flex-start|flex-end|baseline;
```
# <a name="_toc3346"></a>**Justify Content**
justifyContent property is used to determine how should children’s components be aligned within the **primary axis** of their container. It can align children horizontally or vertically within a container. If flexDirection is set to row then alignment will be horizontally else it will be vertically aligned within a container.

**Syntax:**
```
justify-content: flex-start|flex-end|center|space-between|
space-around|space-evenly;
```
# <a name="_toc24009"></a>**Conditional Styling**
Use StyleSheet.create to do style composition like this,make styles for text, valid text, and invalid text.

```
const styles = StyleSheet.create({
    text: {
        height: 40, backgroundColor: 'white', borderRadius: 5, padding: 10, 
    },
    textvalid: {
        borderWidth: 2,
    },
    textinvalid: {
        borderColor: 'red',
    },
});
```

and then group them together with an array of styles.

```
<TextInput
    style={[styles.text, touched && invalid ? styles.textinvalid : styles.textvalid]}
</TextInput>
```

# <a name="_toc21569"></a>**Another Way of passing props**
```
function Search({setterm}){
    const [input, setInput] = useState("")
    
    const handleEndEditing = ()=>{
        if(!input){
            return
        }
        setterm(input);
    }
    return(...);
```

# <a name="_toc25151"></a>**Passing Data**
### <a name="_toc3910"></a>Passing data to parent to child
In React Native, data can be passed from a parent component to a child component using props.

To pass data as a prop from a parent component to a child component, you can follow these steps:

1. Define the data that you want to pass in the parent component. This can be any JavaScript value, such as a string, number, boolean, array, or object.
1. In the parent component, include the child component and pass the data as a prop by adding a prop with a name of your choice and the value set to the data that you want to pass.

For example, if you have a child component named "MyChildComponent" and you want to pass a string "Hello, World!" as a prop named "message", you can include the child component in the parent component like this:

![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/019.png)

3. In the child component, access the data that was passed as a prop using the props object. You can use the name of the prop that you set in the parent component to access the data.

For example, if you want to display the message string that was passed from the parent component, you can access it like this:

![TextDescription automatically generated](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/020.png)

The child component will receive the "message" prop with the value of "Hello, World!" and display it in a Text component.

### <a name="_toc26252"></a>Passing data to child to parent
In React Native, data can be passed from a child component to a parent component using callback functions.

To pass data from a child component to a parent component using a callback function, you can follow these steps:

1. Define a callback function in the parent component that will receive the data from the child component as an argument. This function can be passed as a prop to the child component.

For example, if you have a parent component named "MyParentComponent", you can define a callback function named "handleData" that will receive the data as an argument like this:

![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/021.png)

1. In the child component, define a function that will call the callback function in the parent component and pass the data as an argument. This function can be called in response to some user interaction or other event.

For example, if you have a child component named "MyChildComponent", you can define a function named "sendData" that will call the callback function in the parent component and pass the data as an argument like this:

![](https://github.com/muhammadnaqeeb/React-Native-Notes/blob/main/images/022.png)

1. In the parent component, pass the callback function as a prop to the child component. You can give the prop any name you like, such as "onData", and use it to call the callback function in the parent component when the child component wants to pass data to the parent component.

When the user presses the "Send Data" button in the child component, the "sendData" function will be called, which will call the "handleData" function in the parent component with the data as an argument.

Note that the callback function should be defined in the parent component, so that it has access to the parent component's state and can update it as necessary.
# **Controlled and Uncontrolled Component in React**
In React, a controlled component is a component that is controlled by React state, while an uncontrolled component is a component that maintains its own internal state.

A controlled component receives its current value and an update callback via props, and the parent component manages the state of the component. When the user interacts with the component, the parent component updates the state, which in turn updates the component's value.

An uncontrolled component, maintains its own internal state, and when the user interacts with the component, it updates its own state, which in turn updates the component's value.

|**Features**|**Controlled Component**|**Uncontrolled Component**|
| :-: | :-: | :-: |
|Value Management|Managed by React state|Managed by component's own internal state|
|User Interaction|Parent component updates state on user interaction|Component updates own internal state on user interaction|
|Data Flow|Data flows from parent component to component|Data flows within the component|
|Debugging|Easier to debug|More difficult to debug|
|Performance|Generally faster as there's less state management|Generally slower as there's more state management|
|Code Complexity|Less complex code|More complex code|
|Best Practices|Considered a best practice|Considered an alternate approach|

# **Pure vs impure component**
### Pure Components:
- Relies only on props and doesn't have internal state or dependencies.
- Renders the same output for the same set of props.
- Suitable for presentational or reusable components.
- Preferred when rendering is solely based on props.
- Helps optimize performance by reducing re-renders.

```
import React from 'react';
import { Text } from 'react-native';

const PureExample = ({ name }) => {
  return <Text>Hello, {name}!</Text>;
};

export default React.memo(PureExample);
```

### Impure Components:
- Can have internal state, dependencies, or side effects.
- May re-render even if props haven't changed due to state or external events.
- Can perform side effects using hooks like useEffect.
- Handles complex state management and interactions with external systems.
- Can update UI based on events, fetch data, or maintain component-specific state.
- Suitable for container components or higher-level components.
- Necessary for handling stateful logic and complex interactions.
```
import React, { useState, useEffect } from 'react';
import { Text } from 'react-native';

const ImpureExample = () => {
  const [count, setCount] = useState(0);

  useEffect(() => {
    // Perform side effect, such as fetching data
    // Update count every second
    const interval = setInterval(() => {
      setCount((prevCount) => prevCount + 1);
    }, 1000);

    // Clean up the interval
    return () => clearInterval(interval);
  }, []);

  return <Text>Count: {count}</Text>;
};

export default ImpureExample;
```

# **Themes in React Native Apps**
### Example 1 (changing Theme dark and light)
Create a state variable
```
const [isDarkTheme, setIsDarkTheme] = useState(false);
```
Create function to toggle theme

```
const toggleTheme = () => {
   setIsDarkTheme(!isDarkTheme);
};
```

Create theme style object(above return)
'''
const theme = StyleSheet.create({
    container: {
      flex: 1,
      backgroundColor: isDarkTheme ? 'black' : 'white',
      justifyContent: 'center',
      alignItems: 'center',
    },
    text: {
      color: isDarkTheme ? 'white' : 'black',
      fontSize: 24,
    },
  });
'''
On button press
```
return (
    <View style={theme.container}>
      <Button title="Toggle Theme" onPress={toggleTheme} />
      <Text style={theme.text}>Current Theme: {isDarkTheme ? 'Dark' : 'Light'}</Text>
    </View>
  );
```

Complete code
```
import React, { useState } from 'react';
import { StyleSheet, View, Button, Text } from 'react-native';

export default function App() {
  const [isDarkTheme, setIsDarkTheme] = useState(false);

  const toggleTheme = () => {
    setIsDarkTheme(!isDarkTheme);
  };

  const theme = StyleSheet.create({
    container: {
      flex: 1,
      backgroundColor: isDarkTheme ? 'black' : 'white',
      justifyContent: 'center',
      alignItems: 'center',
    },
    text: {
      color: isDarkTheme ? 'white' : 'black',
      fontSize: 24,
    },
  });
  return (
    <View style={theme.container}>
      <Button title="Toggle Theme" onPress={toggleTheme} />
      <Text style={theme.text}>Current Theme: {isDarkTheme ? 'Dark' : 'Light'}</Text>
    </View>
  );
}
```

### Example 2 (Consistent theme across whole app)
Below import statements make a theme object
```
const MyTheme = {
  dark: false,
  colors: {
    primary: 'rgb(255, 45, 85)',
    background: 'rgb(242, 242, 242)',
    card: 'rgb(255, 255, 255)',
    text: 'rgb(28, 28, 30)',
    border: 'rgb(199, 199, 204)',
    notification: 'rgb(255, 69, 58)',
  },
};
```
In components
```
  return (
    <View style={{ flex: 1, alignItems: 'center', justifyContent: 'center' }}>
      <Text style={{ color: MyTheme.colors.text, fontSize: 24 }}>Details Screen</Text>
      <Button
        title="Go to Settings"
        onPress={() => navigation.navigate('Settings')}
        color={MyTheme.colors.primary}
      />
    </View>
  );
```