<template>
    
<div>
    <!-- Template Syntax -->
    <h1>Template Syntax</h1>

    <!-- a. Text Interpolation - A message showing the value of the msg variable is displayed using text interpolation. -->
    <h2>a. Text Interpolation</h2>
    <p>Text Interpolation - A message showing the value of the msg variable is displayed using text interpolation. </p>
    <span>Message: Hello there! {{ msg }}</span>

    <!-- b. Raw HTML [v-html] - Raw HTML content is displayed using both text interpolation and the v-html directive.-->
    <h2>b. Raw HTML [v-html]</h2>
    <p>Raw HTML content is displayed using:.</p>
    <p>Using text interpolation: {{ rawHtml }}</p>
    <p>Using v-html directive: <span v-html="rawHtml"></span></p>

    <!-- c. Attribute Bindings - Binds the id attribute of a <div> element to the dynamicId variable dynamically. -->
    <h2>c. Attribute Bindings</h2>
    <p>Binds the id attribute of a div element to the dynamicId variable dynamically. </p>
    <div :id="dynamicId"></div>
    
    <!-- d. JavaScript expressions inside syntax i.e {{  }} - Various JavaScript expressions, including mathematical operations, ternary conditions, and string manipulation, are evaluated and displayed-->
    <h2>d. JavaScript Expressions</h2>
    <p>JavaScript expressions inside syntax. Thus includes evaluation of mathematical operations, ternary conditions, and string manipulation to be displayed.</p>
    {{ number + 1 }}
    {{ ok ? 'YES' : 'NO' }}
    {{ message.split('').reverse().join('') }}
    <div :id="`list-${id}`"></div>
</div>

<div>
    <!-- Display the count value - Reactivity is displayed by incrementing a count variable on button click. -->
    <h1>Reactivity Fundamentals</h1>
    <p>Display the count value - Reactivity is displayed by incrementing a count variable on button click. </p>
    <p>Count: {{ count }}</p>
    <button @click="incrementCount">Increment</button>
</div>

<div>
    <!-- Computed Properties - Calculates whether the author has published books and displays a message accordingly by showing a computed property, publishedBooksMessage. -->
    <h1>Computed Properties</h1>
    <p>Computed Properties - Calculates whether the author has published books and displays a message accordingly by showing a computed property, publishedBooksMessage.</p>
    <p>Has published books:</p>
    <span>{{ publishedBooksMessage }}</span>
</div>

<div>
    <!-- Class and Style Bindings - HTML classes are dynamically binded to inline styles based on variables. -->
    <h1>Class and Style Bindings</h1>
    <p>Class and Style Bindings - HTML classes are dynamically binded to inline styles based on variables. </p>
    <h2>a. Binding HTML class</h2>
    <div :class="classObject">Dynamic Class</div>
    <div class="static" :class="classObject">Dynamic Classes with Static Class</div>
    <h2>b. Binding Inline Styles</h2>
    <div :style="{ color: activeColor, fontSize: fontSize + 'px' }">Inline Style 1</div>
    <div :style="{ 'font-size': fontSize + 'px' }">Inline Style 2</div>
    <div :style="styleObject">Inline Style 3</div>
</div>
    <!-- List Rendering - An array of items is iterated through and then a v-for is used to display their messages. -->
    <h1>List Rendering</h1>
    <li v-for="item in items" :key="item.id">{{ item.message }}</li>


    <!-- v-for with an Object - The properties of an object are iterated through and then the key-value paris are displayed -->
    <h2>v-for with an Object</h2>
    <p>The properties of an object are iterated through and then the key-value paris are displayed</p>
    <ul><li v-for="(value, key, index) in myObject" :key="index">{{ index }}. {{ key }}: {{ value }}</li></ul>

    <!-- v-for with an Range - v-for is used to iterate through a range of numbers and display them.-->
    <h2>v-for with a Range</h2>
    <p>v-for is used to iterate through a range of numbers and display them.</p>
    <span v-for="n in 10" :key="n">{{ n }}</span>

    <!-- v-for on <template> - Demonstrates using v-for on a <template> element to conditionally render elements with v-if.-->
    <h2>v-for on template</h2>
    <p>Demonstrates using v-for on a template element to conditionally render elements with v-if.</p>
    
    <!-- v-for with v-if - Conditionally render list items based on a property by combining v-for with v-if.-->
    <h2>v-for with v-if</h2>
    <p>Conditionally render list items based on a property by combining v-for with v-if.</p>
    <template v-for="todo in todos" :key="todo.id">
    <div>
    <li v-if="!todo.isComplete">
    {{ todo.name }}
    </li>
    </div>
    </template>

    <!-- v-for with a Component - v-for is used to iterate and render instances of a custom component, MyComponent.-->
    <h2>v-for with a Component</h2>
    <p>v-for is used to iterate and render instances of a custom component, MyComponent</p>
    <MyComponent v-for="item in items" :key="item.id" />
    <MyComponent v-for="(item, index) in items"
    :item="item"
    :index="index"
    :key="item.id"/>


    <!-- Event Handling - @click is used to handle buttons and invokes methods.-->
    <h1>Event Handling: Listening to Events [v-on:click]</h1>

    <!-- Inline Headers - Two-way data binding is demonstrated using v-model with various input elements.-->
    <p>Inline Headers - Two-way data binding is demonstrated using v-model with various input elements.</p>
    <h2>Inline Headers</h2>
    <button @click="counter++">Add 1</button>
    <p>Count is: {{ counter }}</p>
    
    <!-- Method Handlers -->
    <h2>Method Handlers</h2>
    <button @click="hello">Hello</button>

    <!-- Form Input Bindings -->
    <h1>Form Input Bindings</h1>

    <!-- v-model with text, checkbox, radio, select and textarea -->
    <h2>a. v-model with text, checkbox, radio, select and textarea</h2>
    <p>Say something: {{ saysomething }}</p>
	<input v-model="saysomething" placeholder="here" />

    <!-- v-model modifiers [.lazy , .number, .trim] -->
    <h2>b. v-model modifiers [.lazy , .number, .trim]</h2>
    <input v-model.lazy="msg" />
    <input v-model.number="age" />
    <input v-model.trim="msg" />

    <!-- Watchers - Seeks changes in an input field and asynchronously fetches data based on the input. -->
    <h1>Watchers</h1>
    <p>Seeks changes in an input field and asynchronously fetches data based on the input.</p>
    <p>Ask a yes/no question: <input v-model="question" /></p><p>{{ answer }}</p>
    

    <!-- Components - Interacts with components, including using props to increment a count .-->
    <h1>Components</h1>
    <p>Interacts with components, including using props to increment a count </p>


    <!-- Props -->
    <h2>a. Props</h2>
    <button @click="count2++">You clicked me {{ count2 }} times.</button>

    <!-- Events [$emit] -->
    <h2>b. Events [$emit]</h2>
    <div :style="{ fontSize: postFontSize + 'em' }">
    <BlogPost
    v-for="post in posts"
    :key="post.id"

    :title="post.title"
    /></div>

    <!-- Slots -->
    <h2>c. Slots</h2>


    <!--  Defines routes for navigation between different views in the Vue application. -->
    <h1>Routers</h1>
    <p>Defines routes for navigation between different views in the Vue application</p>

    </template>

    
    
<script setup>
import { ref, reactive, computed, watch } from 'vue';

const number = ref(42);
const ok = ref(true);
const message = ref('Hello, world!');
const count = ref(0);

function incrementCount() {
  count.value++;
}




const author = reactive({
  name: 'John Doe',
  books: [
    'Vue 2 - Advanced Guide',
    'Vue 3 - Basic Guide',
    'Vue 4 - The Mystery'
  ]
});
const publishedBooksMessage = computed(() => {
  return author.books.length > 0 ? 'Yes' : 'No';
});



const isActive = ref(true); // Initially set to true or false
const hasError = ref(false); // Initially set to true or false
// Define a computed property to calculate class binding
const classObject = computed(() => {
  return {
    active: isActive.value,
    'text-danger': hasError.value,
  };
});



const activeColor = ref('red')
const fontSize = ref(30)
const styleObject = reactive({
  color: 'red',
  fontSize: '13px'
});



const myObject = reactive({
  title: 'How to do lists in Vue',
  author: 'Jane Doe',
  publishedAt: '2016-04-10'
});


const counter = ref(0)



const name = ref('Vue.js')

function hello(event) {
  alert(`Hello ${name.value}!`)
  // `event` is the native DOM event
  if (event) {
    alert(event.target.tagName)
  }
}


const saysomething = ref('')




const question = ref('')
const answer = ref('Questions usually contain a question mark. ;-)')

// watch works directly on a ref
watch(question, async (newQuestion) => {
  if (newQuestion.indexOf('?') > -1) {
    answer.value = 'Thinking...'
    try {
      const res = await fetch('https://yesno.wtf/api')
      answer.value = (await res.json()).answer
    } catch (error) {
      answer.value = 'Error! Could not reach the API. ' + error
    }
  }
})



const count2 = ref(0)



    
    
const posts = ref([
  /* ... */
])

const postFontSize = ref(1)


</script>








<style scoped>
h1 {
    margin-top: 80px;
    margin-bottom: 5px;
    font-size: 24px;
    color: #333;
}

h2 {
    font-size: 20px;
    color: #666;
    margin-top: 20px;
    margin-bottom: 10px;
}

p {
    font-size: 16px;
    color: #888;
    margin-bottom: 20px;
}

span {
    font-size: 18px;
    color: #007BFF;
}

button {
    font-size: 16px;
    background-color: #007BFF;
    color: #fff;
    padding: 10px 20px;
    border: none;
    cursor: pointer;
}

button:hover {
    background-color: #0056b3;
}

input[type="text"],
input[type="number"],
input[type="checkbox"],
input[type="radio"],
select,
textarea {
    font-size: 16px;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 5px;
    margin-bottom: 10px;
}

input[type="text"]:focus,
input[type="number"]:focus,
input[type="checkbox"]:focus,
input[type="radio"]:focus,
select:focus,
textarea:focus {
    border: 1px solid #007BFF;
    outline: none;
}

ul {
    list-style: none;
    padding: 0;
}

li {
    margin-bottom: 5px;
}

.container {
    max-width: 800px;
    margin: 0 auto;
    padding: 20px;
}

</style>
