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
        * Can be reused on angular or Vue for instance.
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
Using [Scrimba](https://scrimba.com/learn-Vue-c0jrrpaasr/~0y3o)

* What is Vue js?
    * A friendly and simple javascript framework to help build interfaces
    * Builds on HTML, CSS, and JavaScript
* Setting up Vue js
    * You can use Vue js on html using a [cdn](https://Vuejs.org/guide/quick-start#using-Vue-from-cdn) by putting the following code into your html header...
```html
<script src="https://unpkg.com/Vue@3/dist/Vue.global.js"></script>
```

* How does Vue work?
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
* Importing Vue functions
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

<img width="377" height="250" alt="2025-10-12 17_47_11-Vue js testing and 5 more pages - Personal - Microsoft​ Edge" src="https://github.com/user-attachments/assets/fea091ab-3025-42e5-90f1-27ea5e734e25" />

Here's what the HTML preview would look like.

### 10/13/25: More Vue js practice
Using [Scrimba](https://scrimba.com/learn-Vue-c0jrrpaasr/~0ykp)

* Using return in your app instance
    * When you use "return" for multiple variables in your app instance, you should only have one line with return.
    * Additionally, you should put your variables within the opening and closing of ONE curly bracket.
        * Ex. `return {var1, var2, var3}`
* Reminder: Using a setup function is crucial.
    * This allows your app to run the code you have for your variables.
* Vue reactivity
    * Making parts of you website reactive makes your website dynamic.
    * More powerful and easier to manage due to variables.

* Installing Vue js locally
    * To use Vue js locally, you must use a npm in your terminal.
    * Many local Vue js projects use Vite.
    * Steps in chronological order:
```bash
npm create Vue@latest # to try to get the most up to date version
# use "y" to proceed
# insert the name you'd like for your Vue js project
# answer the questions however you'd like about the features for your project
# up and down arrows to switch between option, space to confirm, and enter for the next step
# repeat for experimental features
cd new-Vue-project-name # go into your new Vue project according to what you named it
npm install
npm run dev # starts development server
```

* If you get an error after the first step, run this:
```bash
npm install -g n
sudo n 20.17.0  # use minimum required version
npm install -g npm@11.6.2 # try to install again
```

### 10/20/25: Vue project anatomy
Using [Scrimba](https://scrimba.com/learn-Vue-c0jrrpaasr/~06ia)

* "src" is the source folder - **where you'll find most of your time building the app!**
    * Holds the assets folder of your project
    * The components folder lives in here, too.
        * Components = chunks of code that'll make up your app interface
* `App.Vue` is the heart of your application - **the main view file**
* `main.js` is the JS file that links your HTML to your Vue project.
    * The importing you'd normally have to do while using a CDN will sit in here.
    ```js
    import { createApp } from 'vue'
    import App from './App.vue'

    createApp(App).mount('#app')
    ```
    * Like the "createApp" and "mount" concepts
* Main HTML page - **where your HTML is mounted to your main JS file**
    * Includes a script tag back to the `main.js` file.
    * Entire Vue app mounted into your "app" div
    ```html
    <div id="app"></div>
    <script type="module" src="/src/main.js"></script>
    ```
* Public folder
    * Where you put your files that you want exposed to the public.
    * Ex. Favicon files
* Config files
    * Includes `jsconfig.json`, `package-loc.json`, `package.json`, and `vite.config.js`
    * Allow Vue to work nicely
    * `jsconfig.json` determines what files should be compiled within the project
    * `package-lock.json` and `package.json` list dependencies like Vue, Vite, developer tools, and scripts.
    * `vite.config.js` holds the configuration settings for Vite (build tool powering the project)
        * Vue and Vue Dev Tools are imported and applied as plugins for Vite
            * Disable either by simply commenting it out or deleting it.
            Example
            ```js
            import { fileURLToPath, URL } from 'node:url'

            import { defineConfig } from 'vite'
            import vue from '@vitejs/plugin-vue'
            <!-- import vueDevTools from 'vite-plugin-vue-devtools' -->

            // https://vite.dev/config/
            export default defineConfig({
            plugins: [
                vue(),
                <!-- vueDevTools(), -->
            ],
            resolve: {
                alias: {
                '@': fileURLToPath(new URL('./src', import.meta.url))
                },
            },
            })
            ```


### x/x/xx: topic
*

<!--
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
