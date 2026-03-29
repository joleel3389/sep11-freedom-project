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
    * In the `main.js` file, ensure that you import a `main.css` file like so
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

### 12/8/25: Code cleaning practice
Used [Scrimba](https://scrimba.com/learn-vue-c0jrrpaasr/~0xt3/s0blb8o0k1/head)

Challenge: follow the Vue mockup using prior knowledge
* Remember to add stuctural components into a components folder

    <img width="279" height="216" alt="2025-12-14 17_11_31-Window" src="https://github.com/user-attachments/assets/5ff6a40c-6c34-4516-9ddc-a17ff4252b2e" />

* Remember to import structural components (Header, Main, Footer)
    ```js
    <script setup>
        /*
        CHALLENGE: Turn the provided HTML/CSS mockup into a Vue app that
                uses three components: Header, Main, and Footer.
                Make sure you use all the provided CSS!
        */
        import Header from '@/components/Header.vue'
        import Main from '@/components/Main.vue'
        import Footer from '@/components/Footer.vue'
    </script>
    ```
* Remember to use the structural components in `App.vue`
    ```html
    <template>
        <Header/>
        <Main/>
        <Footer/>
    </template>
    ```
* Remember to simplify CSS accordingly
    * In `Header.vue` or any of the structural components, remove repetitiveness
        ```css
        <style scoped>
            img {
                height: 150px;
            }
            h1 {
                font-size: 2rem;
                color: #34495e;
                margin-top: 10px;
            }
        </style>
        ```
        * Removed "header" from the beginning of the styles!
* Keep the base CSS as it is in `main.css`
    ```css
    @import url('https://fonts.googleapis.com/css2?family=Inter:ital,opsz,wght@0,14..32,100..900;1,14..32,100..900&display=swap');

    * {
        margin: 0;
        padding: 0;
        font-family: 'Inter', sans-serif;
        box-sizing: border-box;
    }

    body {
        background-color: #40b883;
        min-height: 100vh;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    #app {
        background-color: #eee;
        width: 80%;
        max-width: 700px;
        margin: 0 auto;
        padding: 35px;
        border-radius: 15px;
        display: flex;
        flex-direction: column;
        align-items: center;
        text-align: center;
    }


    span.highlight {
        color: #40b883;
    }
    ```
* Use the rest of the preset code accordingly!

    <img width="600" height="428" alt="2025-12-14 19_18_50-Window" src="https://github.com/user-attachments/assets/d7bc5d05-82af-4195-bb6e-581c4e5c1286" />
    <img width="652" height="510" alt="2025-12-14 19_19_07-Window" src="https://github.com/user-attachments/assets/98e44dbc-12e6-4f2a-95fd-d62b0f5d6200" />
    <img width="890" height="767" alt="2025-12-14 19_19_47-Window" src="https://github.com/user-attachments/assets/d40f47e2-4f35-4f96-8eeb-ac933fc55558" />
    <img width="917" height="610" alt="2025-12-14 19_19_58-Window" src="https://github.com/user-attachments/assets/1ffac98d-7a47-483c-a394-1cad63122ba3" />
    <img width="919" height="418" alt="2025-12-14 19_20_07-Window" src="https://github.com/user-attachments/assets/93bb6416-c030-42c5-97c9-3c97d914c0b0" />

### 12/29/25 - Starting reactivity
Used [Scrimba](https://scrimba.com/learn-vue-c0jrrpaasr/~03af)

* Reactive state summary
    * When you change something about a reactive element, Vue will automatically update it
    * Live and automatic
    * Vue does the work for you, as long as your variable is in a live and reactive state
* Reactive state variables are made using `ref()`
    * To state a constant variable, but to wrap the intended value with `ref()`
* EX
    ```js
    <script setup>
        import {ref} from 'vue'
        const quote = ref("First, solve the problem. Then, write the code.")
    /*
    CHALLENGE: Create a reactive variable to house the author
    */
    </script>
    ```
    * You would look at the reactive quote variable and take inspiration from it like so:
        ```js
        <script setup>
            import {ref} from 'vue'
            const quote = ref("First, solve the problem. Then, write the code.")
            const author = ref("John Johnson")
        /*
        CHALLENGE: Create a reactive variable to house the author
        */
        </script>
        ```
* Ensure that whenever you use a reactive variable, you import `{ref}` in your `<script setup>` tags

### 1/9/26 - Template syntax
Used [Scrimba](https://scrimba.com/learn-vue-c0jrrpaasr/~03ju)

* Rendering reactive elements to the page
* Vue uses an HTML based syntax
    * Allows the binding of data
        * Ex. from refs to certain elements
* How to use a ref?
    * Use double squiggly brackets to replace your hard coded element with the ref name.
        * So if the JS part looks like this, and it's called "title"...
        ```js
        <script setup>
        import {ref} from 'vue'
        const title = ref("Quote Generator")
        </script>
        ```
        * We would go to the HTML part (template) and replace the hard coded title to our ref "title".
        ```html
        <template>
            <header>
                <h1>{{title}}</h1>
            </header>
        </template>
        ```
* If I had title attached to a ref, technically `.value` needs to be used to change its value.
    * Instead of changing the parameter within ref,
        * `const title = ref("Programming quotes")`
    * Change the `.value` of "title" like so...
        * `title.value = "Programming Quotes"`
    * Despite this, it's totally fine to keep "title" within the template/HTML section! Vue will know to update it.
* You do not only need to use strings for your ref, you're free to use booleans, arrays, or numbers.
    * Just remember to use quotations whenever you need them

### 1/9/26 - Template syntax attribute binding
Used [Scrimba](https://scrimba.com/learn-vue-c0jrrpaasr/~03q4)

* We cannot do `<a href="{{href}}">`, so we must bind data to HTML attributes instead.
    * Can be done with v-bind which you attach to HTML attributes like so; `v-bind:href="link"`
        * Put v-bind inside an HTML tag.
        * Will be data bound ot the link in this case.
    * Ex.
    ```js
    <script setup>
        import {ref} from 'vue'
        const quote = ref("First, solve the problem. Then, write the code")
        const author = ref("John Johnson")
        const href = ref("https://en.wikipedia.org/wiki/Undocumented_feature")

        quote.value = "It's a feature, not a bug."
        author.value = "Unknown"
        /*
        CHALLENGE: Turn static author name into a dynamic link
        STEP 1: Create a link Ref
                (use whatever URL you want, or this one: https://en.wikipedia.org/wiki/Undocumented_feature)
        STEP 2: Wrap the author span in anchor tags
        STEP 3: Use v-bind to bind the href attribute to the link Ref
        STEP 4: Fix up the styling
        */
    </script>
    ```
    ```html
    <template>
        <main>
            <section>
                <p>{{quote}}</p>
                <a v-bind:href="href"><span>{{author}}</span></a>
            </section>
            <button>Another!</button>
        </main>
    </template>
    ```
    * Make sure to adjust CSS if needed based on parent child relationships.
* Scope styles allows you to change the CSS of an element super quickly. (Using `<style scoped>`)


<!-- Used [Youtube](https://www.youtube.com/watch?v=5uzbcDHzcc4)

* v-bind acts similar to an electric socket, dynamically connecting the data property to 1 or more element attribute
    * class & style bindings
* To use v-bind, use `v-bind:` before a class attribute, or just a colon `:`
    * By passing an object in, you can dynamically toggle classes.
    ``` -->

### 3/2/26 - progress check & v-bind
Progress... Tried to begin by planning where the question would go and a navigation bar

```html
<nav class="navbar fixed-top bg-body-tertiary navbar-expand-lg" data-bs-theme="dark">
    <div class="container-fluid">
        <span class="navbar-brand mb-0 h1">Calculus study mini-game</span>
        <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
        </button>
        <div class="collapse navbar-collapse" id="navbarSupportedContent">
            <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
            <li class="nav-item">
                <a class="nav-link" aria-current="page" href="https://www.desmos.com/calculator" target="_blank">Calculator</a>
            </li>
            <li class="nav-item">
                <a class="nav-link" href="#help">Need help?</a>
            </li>
            </ul>
        </div>
    </div>
</nav>

<div class="container-fluid">
    <div class="container" id="#questionaire">
    <h2 class="text-dark">Placeholder question?</h2>
    <input type="radio" name="mcq" value="1" id="Option1"> placeholder <br>
    <input type="radio" name="mcq" value="2" id="Option2"> placeholder <br>
    <input type="radio" name="mcq" value="3" id="Option3"> placeholder <br>
    <input type="radio" name="mcq" value="4" id="Option4"> placeholder <br>
    <!-- Each one has the same TYPE and NAME, so that the user can only select ONE option -->

    <br>
    <button>Submit</button>
    <br>
    <p></p>
    </div>
</div>
```

Used [Scrimba](https://scrimba.com/learn-vue-c0jrrpaasr/~06vz)

* `v-bind` works with boolean attributes
    * Attributes like disabled, as long as the `ref()` feeding it is a boolean.
    * Will action accordingly
    * Ex. `const isBtnDisabled = ref(false)`, `v-bind:disabled="isBtnDisabled"`
        * the disabled attribute will be FALSE, so the button will NOT be disabled.
* `v-bind` has "shorthands"
    * Instead of `v-bind:`, just begin with a colon followed by the attribute like so- `:attribute`
        * In full, `v-bind:attribute="value"` is shortened to `:attribute="value"`
        * Of course, it functions the SAME exact way
* If attribute (name) = value (that you're passing), you can remove the equal sign AND value.
    * Ex. Instead of `:hef="href"`, we can use `:href` and it'll be the SAME

Used [Scrimba](https://scrimba.com/learn-vue-c0jrrpaasr/~07cp)

* Challenge 1
```js
<script setup>
  /*
CHALLENGE: Create a Ref to house "https://vuejs.org/"
           and bind the Ref to our anchor tag's href attribute.
           Use shorthands if you want/can!
*/
import {ref} from 'vue'
const href = ref("https://vuejs.org/")
</script>
```
```html
<template>
  <footer>
      <p>Learn more about me at <a target="_blank" :href>vuejs.org</a></p>
  </footer>
</template>
```

* Reactive array
```js
<script setup>
/*
CHALLENGE: Create a reactive array of objects to house the Vue facts
TIP: Each object might have a an "adjective" property and "description" property
*/

import {ref} from 'vue'
const facts = ref([
  {
    "adjective": "Lightweight",
    "description": "I am incredibly small and fast! My core library is only around 30KB, so I won't slow you down."
  },
  {
    "adjective": "Approachable",
    "description": "Easy to learn and use, even for beginners. I have a gentle learning curve, clear documentation, and a supportive community."
  },
  {
    "adjective": "Versatile",
    "description": "I can handle everything from simple interactive elements to complex single-page applications. I'm great for small projects and large-scale applications alike."
  },
])
/*
CHALLENGE: Bind the data from the `facts` Ref to elements in the template
*/
</script>
```
```html
<template>
  <main>
      <section>
          <h2>
              I'm <span class="highlight">{{facts[0].adjective}}</span>
          </h2>
          <p>{{facts[0].description}}</p>
      </section>
      <section>
          <h2>
              I'm <span class="highlight">{{facts[1].adjective}}</span>
          </h2>
          <p>{{facts[1].description}}</p>
      </section>
      <section>
          <h2>
              I'm <span class="highlight">{{facts[2].adjective}}</span>
          </h2>
          <p>{{facts[2].description}}</p>
      </section>
  </main>
</template>
```

### 3/16/26 - Progress check and more Vue
Progress check

In order to use Vue, I moved a temporary Vue file I already made up so that I could use it for my main `index.html` file instead. (This is so I wouldn't have had to use a CDN.)

Then, with the old Navbar I made originally, I moved my original code into a `Navbar.vue` component like so:

```html
<template>
    <nav class="navbar fixed-top bg-body-tertiary navbar-expand-lg" data-bs-theme="dark">
        <div class="container-fluid">
            <span class="navbar-brand mb-0 h1">Calculus study mini-game</span>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
            <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav ms-auto mb-2 mb-lg-0">
                <li class="nav-item">
                    <a class="nav-link" aria-current="page" href="https://www.desmos.com/calculator" target="_blank">Calculator</a>
                </li>
                <li class="nav-item">
                    <a class="nav-link" href="#help">Need help?</a>
                </li>
                </ul>
            </div>
        </div>
    </nav>
</template>
```

And I moved all of my CSS into `main.css` so I could use it globally.
 ```css
    .text-light{
    color:#F2F3F1;
}
.text-dark{
    color: #1C1921;
}
.suva-gray {
    color: #838183 !important;
}
.oslo-gray {
    color: #cad9d0 !important
}
.container {
    padding: 150px 0px 30px 300px;
    margin: auto;
}
#questionaire {
    margin: auto;
    text-align: center;
    padding: 30px 0px 100px 0px;
}
input {
    color: #F2F3F1;
}
```

Of course, I made sure to import both Vue component files in `App.vue`
```js
<script setup>
import Navbar from '@/components/Navbar.vue'
import Main from '@/components/Main.vue'
</script>
```

Additionally, I made a reactive array to hold all of the questions (10), and will allow for the indexes to change later.
```js
<script setup>
    import {ref} from 'vue'
    const questionaire = ref([
    {
        "question": "What's the angle at 3π/4?",
        choices: ["175°","150°","135°","120°"]
    },
    {
        "question": "What's the angle jump at every π/4th of a jump?",
        choices: ["45°","25°","30°","60°"]
    },
    {
        "question": "What are the coordinates of 11π/6?",
        choices: ["(√3/2, -1/2)","(√3/2, 1/2)","(√2/2, -√2/2)","(√2/2, √2/2)"]
    },
    {
        "question": "What's the angle at 7π/6?",
        choices: ["240°","210°","180°","225°"]
    },
    {
        "question": "What's the angle jump at every π/6th?",
        choices: ["30°","60°","90°","15°"]
    },
    {
        "question": "What's the angle jump at every π/2th?",
        choices: ["30°","60°","90°","15°"]
    },
    {
        "question": "What's the angle jump at every π/3th?",
        choices: ["30°","60°","90°","15°"]
    },
    {
        "question": "What are the coordinates of 5π/4?",
        choices: ["(-√3/2, -1/2)","(√3/2, 1/2)","(-√2/2, -√2/2)","(√2/2, √2/2)"]
    },
    {
        "question": "What are the coordinates of 2π/3?",
        choices: ["(1/2, √3/2)","(-1/2, √3/2)","(-√2/2, √2/2)","(√2/2, √2/2)"]
    },
    {
        "question": "What's the angle at 5π/3?",
        choices: ["270°","330°","300°","315°"]
    },
    ])
</script>
```

```html
<template>
    <div class="container-fluid">
        <div class="container" id="#questionaire">
        <h2 class="text-dark">{{questionaire[0].question}}</h2>
        <input type="radio" name="mcq" value="1" id="Option1"> {{questionaire[0].choices[0]}} <br>
        <input type="radio" name="mcq" value="2" id="Option2"> {{questionaire[0].choices[1]}} <br>
        <input type="radio" name="mcq" value="3" id="Option3"> {{questionaire[0].choices[2]}} <br>
        <input type="radio" name="mcq" value="4" id="Option4"> {{questionaire[0].choices[3]}} <br>
        <!-- Each one has the same TYPE and NAME, so that the user can only select ONE option -->

        <br>
        <button>Submit</button>
        <br>
        <p></p>
        </div>
    </div>
</template>
```

Current state of my project:
<img width="1666" height="920" alt="2026-03-20 16_32_34-Window" src="https://github.com/user-attachments/assets/07fa0b3b-5d64-4739-bbca-d523934d77ad" />

Used [Official Vue documentation](https://vuejs.org/guide/essentials/class-and-style.html)

* Using `v-bind`, shorten `v-bind:class` to `:class`
    * To dynamically toggle classes.    

### 3/23/26 - Learning more Vue and progress check
Used [Official Vue documentation](https://vuejs.org/guide/essentials/conditional.html)

* Use `v-if` to check that if the value is true, then allow the block to render.
    * Ex. `v-if="yes"`, then the block it's associated with will activate. 
* Use `v-else` if the value is not true, then this block will render instead. 
    * MUST follow a `v-if` or `v-else-if` prior to it.
* Use `v-else-if` to check that if an ADDITIONAL value is true, then allow the block to render.
    * MUST follow a `v-if` or another `v-else-if` prior to it. 

Learned how `v-if` (conditional rendering) can apply to elements.

Used [Official Vue documentation](https://vuejs.org/guide/essentials/forms.html#radio)

* `v-model` can be used on different input types
    * For my case, radio buttons, it can be used to determine which radio button was selected
    * Ex. 
    ```html
    <div>Picked: {{ picked }}</div>

    <input type="radio" id="one" value="One" v-model="picked" />
    <label for="one">One</label>

    <input type="radio" id="two" value="Two" v-model="picked" />
    <label for="two">Two</label>
    ```

**Progress check:**
* I made new reactive variables in order to determine whether the user's choice was correct or wrong.
* To check whether the user's choice was actually the right answer, I used a function with an if statement to see if the user's choice matched the correct answer I defined with each question.
    * If the correct answer matched, then `correct` would be set to true, and it'll progress to the next question. I also allowed for a `v-if` statement that would toggle if `correct` was true, indicating the correct answer was chosen.
    * If the correct answer didn't match, `correct` is set to false and `wrong` is set to true, not progressing to the next question, and with `v-else-if` I enabled text that indicated the wrong answer was chosen.
* I used `v-model` to track the user's choice
* I used the `@click` event handler to run the `checkAnswer()` function whenever the user tried to submit their answer.

JavaScript portion:
```js
<script setup>
    const questionNumber = ref(0);
    const userChoice = ref();
    const correct = ref(false);
    const wrong = ref(false);

    function checkAnswer(){
        if(userChoice.value === questionaire.value[questionNumber.value].correct){
            correct.value = true;
            wrong.value = false;
            questionNumber.value++;
        } else {
            wrong.value = true;
            correct.value = false;
        }
    }
    
    import {ref} from 'vue'
    const questionaire = ref([
        {
            "question": "What's the angle at 3π/4?",
            choices: ["175°","150°","135°","120°"],
            correct: "135°"
        },
        {
            "question": "What's the angle jump at every π/4th of a jump?",
            choices: ["45°","25°","30°","60°"],
            correct: "45°"
        },
        {
            "question": "What are the coordinates of 11π/6?",
            choices: ["(√3/2, -1/2)","(√3/2, 1/2)","(√2/2, -√2/2)","(√2/2, √2/2)"],
            correct: "(√3/2, -1/2)"
        },
        {
            "question": "What's the angle at 7π/6?",
            choices: ["240°","210°","180°","225°"],
            correct: "210°"
        },
        {
            "question": "What's the angle jump at every π/6th?",
            choices: ["30°","60°","90°","15°"],
            correct: "30°"
        },
        {
            "question": "What's the angle jump at every π/2th?",
            choices: ["30°","60°","90°","15°"],
            correct: "90°"
        },
        {
            "question": "What's the angle jump at every π/3th?",
            choices: ["30°","60°","90°","15°"],
            correct: "60°"
        },
        {
            "question": "What are the coordinates of 5π/4?",
            choices: ["(-√3/2, -1/2)","(√3/2, 1/2)","(-√2/2, -√2/2)","(√2/2, √2/2)"],
            correct: "(-√2/2, -√2/2)"
        },
        {
            "question": "What are the coordinates of 2π/3?",
            choices: ["(1/2, √3/2)","(-1/2, √3/2)","(-√2/2, √2/2)","(√2/2, √2/2)"],
            correct: "(-1/2, √3/2)"
        },
        {
            "question": "What's the angle at 5π/3?",
            choices: ["270°","330°","300°","315°"],
            correct: "300°"
        },
    ])
</script>
```

HTML portion:
```html
<template>
    <div class="container-fluid">
        <div class="container" id="#questionaire">
        <h2 class="text-dark">{{questionaire[questionNumber].question}}</h2>
        <input type="radio" name="mcq" :value="questionaire[questionNumber].choices[0]" id="Option1" v-model="userChoice"> {{questionaire[questionNumber].choices[0]}} <br>
        <input type="radio" name="mcq" :value="questionaire[questionNumber].choices[1]" id="Option2" v-model="userChoice"> {{questionaire[questionNumber].choices[1]}} <br>
        <input type="radio" name="mcq" :value="questionaire[questionNumber].choices[2]" id="Option3" v-model="userChoice"> {{questionaire[questionNumber].choices[2]}} <br>
        <input type="radio" name="mcq" :value="questionaire[questionNumber].choices[3]" id="Option4" v-model="userChoice"> {{questionaire[questionNumber].choices[3]}} <br>
        <!-- Each one has the same TYPE and NAME, so that the user can only select ONE option -->

        <br>
        <button class="btn btn-secondary" @click="checkAnswer()">Submit</button>
        <br>
        <p v-if="correct">Correct!</p>
        <p v-else-if="wrong">Incorrect! Try again.</p>
        </div>
    </div>
</template>
```



<!--
* Links you used today (websites, videos, etc)
* Things you tried, progress you made, etc
* Challenges, a-ha moments, etc
* Questions you still have
* What you're going to try next
-->
