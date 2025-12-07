# Tool Learning Log

## Tool: **Vue JS**

## Project: **Calculus concepts memorization game**

---

### 9/29/25: Testing React JS
* What are components in React JS
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
<script src="https://unpkg.com/react@18/umd/react.development.JS"></script>
<script src="https://unpkg.com/react-dom@18/umd/react-dom.development.JS"></script>
<script src="https://unpkg.com/@babel/standalone/babel.min.JS"></script>
```

* In order to use components, you must have a root component.
    * Once you have a root component, you can put other components inside it.
For example, the use of `<Home />` within my root component "App"
```JS
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
```JS
ReactDOM.render(<App />, document.querySelector("#app"));
```

* If you use separate .JS files for your components, they must be linked onto your html page using `src="filename.JS"` like so,
```html
<script type="text/babel" src="App.JS"></script>
<script type="text/babel" src="Home.JS"></script>
```

If your components are properly "rendered" then your html page should show your components, like this for example:

<img width="377" height="149" alt="2025-10-02 18_26_06-Hello World and 4 more pages - Personal - Microsoft​ Edge" src="https://github.com/user-attachments/assets/0b638839-3b76-47e5-8830-f2f80f45693e" />


### 10/6/25: Testing Vue JS
Using [Scrimba](https://scrimba.com/learn-Vue-c0jrrpaasr/~0y3o)

* What is Vue JS?
    * A friendly and simple javascript framework to help build interfaces
    * Builds on HTML, CSS, and JavaScript
* Setting up Vue JS
    * You can use Vue JS on html using a [cdn](https://VueJS.org/guide/quick-start#using-Vue-from-cdn) by putting the following code into your html header...
```html
<script src="https://unpkg.com/Vue@3/dist/Vue.global.JS"></script>
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
```JS
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

```JS
const { createApp, ref } = Vue
createApp({
    setup() {
        const name = ref("Jolee")
        return {name}
    }
}).mount("#myApp")
```

Once you add it all up, it should look something like the code above. It'll work together to allow the variable that you just set a value for to show up on your HTML preview.

<img width="377" height="250" alt="2025-10-12 17_47_11-Vue JS testing and 5 more pages - Personal - Microsoft​ Edge" src="https://github.com/user-attachments/assets/fea091ab-3025-42e5-90f1-27ea5e734e25" />

Here's what the HTML preview would look like.

### 10/13/25: More Vue JS practice
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

* Installing Vue JS locally
    * To use Vue JS locally, you must use a npm in your terminal.
    * Many local Vue JS projects use Vite.
    * Steps in chronological order:
```bash
npm create Vue@latest # to try to get the most up to date version
# use "y" to proceed
# insert the name you'd like for your Vue JS project
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
* `main.JS` is the JS file that links your HTML to your Vue project.
    * The importing you'd normally have to do while using a CDN will sit in here.
    ```JS
    import { createApp } from 'vue'
    import App from './App.vue'

    createApp(App).mount('#app')
    ```
    * Like the "createApp" and "mount" concepts
* Main HTML page - **where your HTML is mounted to your main JS file**
    * Includes a script tag back to the `main.JS` file.
    * Entire Vue app mounted into your "app" div
    ```html
    <div id="app"></div>
    <script type="module" src="/src/main.JS"></script>
    ```
* Public folder
    * Where you put your files that you want exposed to the public.
    * Ex. Favicon files
* Config files
    * Includes `JSconfig.JSon`, `package-loc.JSon`, `package.JSon`, and `vite.config.JS`
    * Allow Vue to work nicely
    * `JSconfig.JSon` determines what files should be compiled within the project
    * `package-lock.JSon` and `package.JSon` list dependencies like Vue, Vite, developer tools, and scripts.
    * `vite.config.JS` holds the configuration settings for Vite (build tool powering the project)
        * Vue and Vue Dev Tools are imported and applied as plugins for Vite
            * Disable either by simply commenting it out or deleting it.
            Example
            ```JS
            import { fileURLToPath, URL } from 'node:url'

            import { defineConfig } from 'vite'
            import vue from '@viteJS/plugin-vue'
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

### 10/27/25: Introduction to functions in Vue JS
Used [Scrimba](https://scrimba.com/learn-vue-c0jrrpaasr/~02zo)
* App.vue -> where most of your work will be done
    * Script tag holds JS
    * Template tag holds HTML
    * Style tag holds CSS
* Use `npm run dev` to see your preview. (not `http-server`)
* By using Vue locally, you no longer need to mount, use functions, or more code than you need to.
    * You can simply import what you want to use and define variables in your JS section.
* The setup keyword in our JS section of App.vue makes code simpler on the local Vue JS.
    * Seen like `<script setup></script>`
* Using `<template></template>` removes any need of having to use meta tags in an HTML header.
* CSS is conviently in the same App.vue file as JS and HTML.

Practice: follow the challenge
* Instructions (JS)
```js
<script setup>
/*
CHALLENGE: Make the copyright year dynamic and blue
IN SCRIPT: Create a new ref to house a different year
IN TEMPLATE: Change the static "2025" to render the new ref
IN STYLE: Target the paragraph tag in the footer and make it blue
*/
  import {ref} from 'vue'
  const name = ref('Rachel')
  const emoji = ref('✌🏻')
</script>
```
* HTML starter code
```html
<template>
  <header>
    <span>{{emoji}}</span>
  </header>

  <main>
    <h1>Hello, {{name}}!</h1>
    <p>I'm about to learn <a href="https://vuejs.org/" target="_blank">Vue.js</a>!</p>
  </main>

  <footer>
    <p>&copy; 2025</p>
  </footer>
</template>
```
* CSS starter code
```css
<style scoped>
  header span{
    font-size:3rem;
  }
  main h1{
      display:block;
  }
  main a{
      color: #42B883;
  }
  footer {
      position:fixed;
      bottom:0;
      padding-bottom:20px;
  }
</style>
```

* To create a new ref, I created a new constant ref named "year" and defined it to be "2026"
    * Creating a ref is kind of similar to JS variables.
        * You can refer to them in your HTML part with `{{variableName}}`
    * I didn't need to use `.mount` since I'm not using a CDN here and it felt more easier to navigate.
    ```js
    <script setup>
    /*
    CHALLENGE: Make the copyright year dynamic and blue
    IN SCRIPT: Create a new ref to house a different year
    IN TEMPLATE: Change the static "2025" to render the new ref
    IN STYLE: Target the paragraph tag in the footer and make it blue
    */
    import {ref} from 'vue'
    const name = ref('Rachel')
    const emoji = ref('✌🏻')
    const year = ref('2026')
    </script>
    ```
* I then made sure I referenced this ref I created in the HTML portion (template), otherwise it wouldn't have showm up
    * Referred to the same ref I had just created in my JS script tags
    ```html
    <template>
    <header>
        <span>{{emoji}}</span>
    </header>

    <main>
        <h1>Hello, {{name}}!</h1>
        <p>I'm about to learn <a href="https://vuejs.org/" target="_blank">Vue.js</a>!</p>
    </main>

    <footer>
        <p> &copy; {{year}} </p>
    </footer>
    </template>
    ```
* After, I made sure to specify the paragraph tag in the footer, so I could recolor it to blue
    * You can specifically identify an element tag without the use of class or id by identifying the tag it was inside.
        * I observed this after reading the rest of the starter code
        * This p tag was inside the footer, so I put "footer p"
        * Most likely only works if you have one of that element within a section.
    ```css
    <style scoped>
    header span{
        font-size:3rem;
    }
    main h1{
        display:block;
    }
    main a{
        color: #42B883;
    }
    footer {
        position:fixed;
        bottom:0;
        padding-bottom:20px;
    }
    footer p{
        color:blue;
    }
    </style>
    ```

### 11/10/25: topic
Used [Scrimba](https://scrimba.com/learn-vue-c0jrrpaasr/~05kv)

* Layout/structural components - not much logic
    * Header
    * Main
    * Footer
* Naming convention looks like `Capitalize.vue`
* Each component has its own script setup, template, and style scope unique to and used by that component.
* Ensure to import a Vue function whenever you use it.
    * For example,
    ```js
    import {ref} from 'vue'
    const emoji = ref('✌`)
    ```
* When you move a structural component and want it to appear on your `App.vue`, you must import it.
    * Example
    ```js
    import Header from `@/components/Header.vue'
    // "Header" refers to the name of the component
    //
    ```
    * You can then use this by typing the tag into your HTML/template section on your actual `App.vue`.
        * If it was named "Header" like in the previous example, use `<Header/>`
            * Capitalize the first word to match the typical Vue JS naming convention.
* The purpose of `App.vue` is to bring the header, main, and footer components together.
* Full example
```js
<script setup>
  import Header from '@/components/Header.vue'
  import Main from '@/components/Main.vue'
  import Footer from '@/components/Footer.vue'
/*
CHALLENGE: Separate the <main> and <footer> elements into
           <Main/> and <Footer/> components and use them
           in App.vue

STEP 1: Create the component file in /components
STEP 2: Set up the script/template/style skeleton
STEP 3: Pull the relevant JS, HTML and CSS into the component
STEP 4: Import component back in App.vue
STEP 5: Use component in App.vue template
*/
</script>
```
```html
<template>

  <Header/>
  <Main/>
  <Footer/>

</template>
```
* The child components were moved into their respective component folders with their corresponding elements.

My application:
* Before

    <img width="1348" height="586" alt="Screenshot 2025-11-10 11 53 15 AM" src="https://github.com/user-attachments/assets/de6dc4f7-814d-40c7-bf90-63d350a07d2a" />

* JavaScript
```js
<script setup>
    /*
    import {ref} from 'vue'
    const name = ref('Jolee')
    const emoji = ref('✌🏻')
    const year = ref('2030')
    */

    import Header from '@/components/Header.vue'
    import Main from '@/components/Main.vue'
    import Footer from '@/components/Footer.vue'
</script>
```

* HTML
```html
<template>
    <Header/>
    <Main/>
    <Footer/>
    <!--
    <header>
        <span>{{emoji}}</span>
    </header>
    -->

    <!--
    <main>
        <h1>Hello, {{name}}!</h1>
        <p>I'm about to learn <a href="https://vuejs.org/" target="_blank">Vue.js</a>!</p>
    </main>
    -->

    <!--
    <footer>
        <p> &copy; {{year}} </p>
    </footer>
    -->
</template>
```

* CSS
```css
<style scoped>
    /*
    header span{
        font-size:3rem;
    }
    */

    /*
    main h1{
        display:block;
    }
    main a{
        color: #42B883;
    }
    */

    /*
    footer {
        position:fixed;
        bottom:0;
        padding-bottom:20px;
    }
    footer p{
        color:blue;
    }
    */
</style>
```

* After preview

    <img width="1348" height="586" alt="Screenshot 2025-11-10 11 53 15 AM" src="https://github.com/user-attachments/assets/52e156c9-b2f5-4dd4-91cf-aace9f279617" />

    * Preview is the same before and after, so we know that the structural components are working.

### 11/17/25: The @ alias
Used [Scrimba](https://scrimba.com/learn-vue-c0jrrpaasr/~05xz)
* The `@` character is apart of the file path
    * However, you can still use the well known `./` as your path indicator, and it'll still work.
        * Start from the current directory and traverse from there
    * For example, changing from this
    ```js
    <script setup>
        import Header from '@/components/Header.vue'
        import Main from '@/components/Main.vue'
        import Footer from '@/components/Footer.vue'
    </script>
    ```
    * To this technically will still work since `App.vue` sits in the `src/` folder.
    ```js
    <script setup>
        import Header from './components/Header.vue'
        import Main from './components/Main.vue'
        import Footer from './components/Footer.vue'
    </script>
    ```
    * This is called relative traversing, but it's not very helpful for more complicated apps.
* More about the `@` alias given by Vite
    * Seen in the `vite.config.js` file, within these three lines of code:
    ```js
    alias: {
      '@': fileURLToPath(new URL('./src', import.meta.url))
    },
    ```
    * Creates a shortcut for our project
    * Means replace `@` for the absolute file path to the `src/` folder
    * In short, it creates a URL to the `src/` folder

Used [Scrimba](https://scrimba.com/learn-vue-c0jrrpaasr/~0gk)
* Creating Vue project from scratch
```bash
npm create vue
cd vue-project
npm install
npm run dev
```
* When you import structural components, you must create a folder for those components with files named after `.vue`
    * If not using variables, nothing needs to go into the script.
* Ex. `Header.vue`
```js
<script setup>
</script>
```
* Copy HTML into `Header.vue`
```html
<template>
    <header>
        <h1>Quote generator</h1>
    </header>
</template>
```
* Copy CSS into `Header.vue`
```css
<style scoped>
  header {
    color:#CCD6D9;
    margin-bottom:25px;
  }
</style>
```

* In the main `App.vue`, just import
```js
<script setup>
    import Header from '@/components/Header.vue'
</script>
```

### 12/1/25: more vue components practice
Used [Scrimba](https://scrimba.com/learn-vue-c0jrrpaasr/~05ho)

* What if we want to apply base styling/CSS?
    * Won't work if you just put it in a `<style scoped>` tag in the `App.vue` file, since "scoped" means it'll only apply to the current component.
* `main.js`is where our `Vue.app` is created
    * Mounts HTML
    * Imports CSS
        * Where we should put our base CSS/styling
* How can we save our base css?
    * In the `main.js` file, ensure that you import a `main.css` file
    ```js
    import './assets/main.css'

    import { createApp } from 'vue'
    import App from './App.vue'

    createApp(App).mount('#app')

    /*
    CHALLENGE: Apply the mockup's base styles to the Vue App
    */
    ```
    * Then, go to your `main.css` file and put your base styling there
    ```css
    *{
    box-sizing: border-box;
    margin: 0;
    padding: 0;
    }

    body{
        background-color:#406473;
        font-family: sans-serif;
    }

    #app {
        display:flex;
        flex-direction:column;
        align-items:center;
        padding:25px;
    }
    ```
    * This is the base styling because it targets the body, app id, and uses the universal selector
* If you have a targetted line of CSS, like `footer span` and import the footer, you don't need to repeat "footer" in your `Footer.vue` file.
    * It makes more sense to specify a parent in a regular `style.css` file, if we were to compare it. 

### x/x/xx: topic
*

<!--
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
