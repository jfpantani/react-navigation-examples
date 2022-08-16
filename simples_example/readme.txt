Hello React Navigation

In a web browser, you can link to different pages using an anchor (<a>) tag. When the user clicks on a
link, the URL is pushed to the browser history stack. When the user presses the back button, the browser
pops the item from the top of the history stack, so the active page is now the previously visited page.
React Native doesn't have a built-in idea of a global history stack like a web browser does -- this is 
where React Navigation enters the story.

React Navigation's native stack navigator provides a way for your app to transition between screens and 
manage navigation history. If your app uses only one stack navigator then it is conceptually similar to 
how a web browser handles navigation state - your app pushes and pops items from the navigation stack as 
users interact with it, and this results in the user seeing different screens. A key difference between 
how this works in a web browser and in React Navigation is that React Navigation's native stack navigator
provides the gestures and animations that you would expect on Android and iOS when navigating between 
routes in the stack.

Let's start by demonstrating the most common navigator, createNativeStackNavigator.

Installing the native stack navigator library​
The libraries we've installed so far are the building blocks and shared foundations for navigators, and 
each navigator in React Navigation lives in its own library. To use the native stack navigator, we need 
to install @react-navigation/native-stack :

npm
Yarn
npm install @react-navigation/native-stack
💡 @react-navigation/native-stack depends on react-native-screens and the other libraries that we 
installed in Getting started. If you haven't installed those yet, head over to that page and follow the 
installation instructions.

Creating a native stack navigator​
createNativeStackNavigator is a function that returns an object containing 2 properties: Screen and 
Navigator. Both of them are React components used for configuring the navigator. The Navigator should 
contain Screen elements as its children to define the configuration for routes.

NavigationContainer is a component which manages our navigation tree and contains the navigation state. 
This component must wrap all navigators structure. Usually, we'd render this component at the root of our
app, which is usually the component exported from App.js.
