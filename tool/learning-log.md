# Tool Learning Log

## Tool: **Vue js**

## Project: **Calculus concepts memorization game**

---

### 9/29/25: Testing React js
* What are components in React js
    * Piece of the user interface that plays its own role on your website. Has a unique appearance and function.
    * Can be as small as a button or as big as your page.
    * Components must start with a capital letter
* Components help you make "parts" that you can use for a bigger and more complex UI
    * This code is meant to be reusable
        * Can be reused on angular or vue for instance.
* How do you set up React?
    * To test react, use the code below in the header of your HTML.
    * You must also set the type of your script to babel
        * Like so, `<script type="text/babel">`
```html
<script src="https://unpkg.com/react@18/umd/react.development.js"></script>
<script src="https://unpkg.com/react-dom@18/umd/react-dom.development.js"></script>
<script src="https://unpkg.com/@babel/standalone/babel.min.js"></script>
```

* In order to use components, you must have a root component.
    * Once you have a root component, you can put other components inside it.
For example, the use of `<Home />` within my root component "App"
```js
   function App() {
        return (
            <div>
              <h1>Welcome to my test app</h1>
              <Home />
            </div>
        );
      }
```

* Use the function line to name your component
* Add return so the component appears on your `http-server`.

* Components must also include a react dom render.
    * Use the name of your root component so all the components including it and within it will appear on when you're viewing your HTML page.
```js
ReactDOM.render(<App />, document.querySelector("#app"));
```

* If you use separate .js files for your components, they must be linked onto your html page using `src="filename.js"` like so,
```html
<script type="text/babel" src="App.js"></script>
<script type="text/babel" src="Home.js"></script>
```

If your components are properly "rendered" then your html page should show your components, like this for example:

<img width="377" height="149" alt="2025-10-02 18_26_06-Hello World and 4 more pages - Personal - Microsoft​ Edge" src="https://github.com/user-attachments/assets/0b638839-3b76-47e5-8830-f2f80f45693e" />


### 10/6/25: Testing Vue js
* What is Vue js?
    * A friendly and simple javascript framework to help build interfaces
    * Builds on HTML, CSS, and JavaScript
* Setting up Vue js
    * You can use Vue js on html using a [cdn](https://vuejs.org/guide/quick-start#using-vue-from-cdn) by putting the following code into your html header...
```html
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
```

* How does vue work?
    * Vue will usually attach itself to a specific part of your HTML, then controlling whatevers inside. This is most commonly a `<div>`. For example,
```html
<div id="app">
    <h1>Welcome name!</h1>
</div>
```

* Vue text interpolation syntax
    * Allows Vue to render the value of a variable within an HTML element
        * Use it by surrounding your variable with a double curly bracket on both sides. Such as `{{number}}` or ``{{name}}``
        * You will then be able to properly define this variable in your JavaScript "script" tags.
* Importing vue functions
    * You can import Vue functions into the script tag of your HTML page shown below
        * This allows you to actually use these functions on your page
```js
const { createApp, ref } = Vue
```

* Vue app instance
    * After importing `createApp`, open a parentheses curly bracket to define the function behavior on your app.
* The `setup() {}` function allows your changes to apply as soon as you reload your site.
    * You should put data inside this function.
* You can use `ref("valueName")` as a view variable, for simple variables like `{{name}}` or maybe `{{number}}`
* You must return your variables so the HTML can access it using `return {variableName}`
    * This returns the data so it can actually show on your HTML page
* As a final touch, use `.mount("#divId")` to be able to apply it to your desired div or the element you've attached Vue to.
    * Mount connects all of the code inside of your app instance.
    * Vue will take over the element it's attached to, and then applies all set and returned changes to your HTML page in real time.

```js
const { createApp, ref } = Vue
createApp({
    setup() {
        const name = ref("Jolee")
        return {name}
    }
}).mount("#myApp")
```

Once you add it all up, it should look something like the code above. It'll work together to allow the variable that you just set a value for to show up on your HTML preview.

<img width="810" height="528" alt="2025-10-12 17_47_11-vue js testing and 5 more pages - Personal - Microsoft​ Edge" src="https://github.com/user-attachments/assets/fee37a57-c03b-4c21-8da1-51d7fd4b5946" />

Here's what the HTML preview would look like.

### x/x/xx: topic
*

<!--
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
