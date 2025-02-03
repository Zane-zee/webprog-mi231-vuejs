<template>
<div class="container">
<h1>Personal Profile Web page </h1>    

    <h2>About Me</h2>  
    <p>Hello! I’m Zane, a passionate IT student specializing in Mobile and Internet Technologies.</p>
    <h2>Education</h2>
    <ul>
        <li>STI College Pasay-EDSA (SHS STEM)</li>
        <li>Asia Pacific College (2nd Year)</li>
    </ul>
    
    <h2>Course</h2>
    <p>Bachelor of Science in Information Technology with specialization in Mobile and Internet Technologies</p>    
    
    <h2>IT Experience</h2>
    <ul>
        <li>Basic Codes of Java</li>
        <li>Basic Codes of Python</li>
        <li>Basic Knowledge in Figma</li>
        <li>Created an app using Figma & Android Studio</li>
    </ul>
    
    <h2>Hobbies & Interests</h2>
    <ul>
        <li>Going to the gym</li>
        <li>Playing Video Games</li>
        <li>Streaming</li>
    </ul> 
    
    <h2>Goals in Life / Dream</h2>
    <p>To become a successful software developer and create apps that positively impact people's lives.</p>  
    
    <div id="app">
        {{ message }} <br>
        {{'Random number: ' + Math.ceil(Math.random()*6) }}
        <div v-bind:class="vueClass">This element is bound to the "pinkBG" class.</div>
      </div>

      <div id="app2">
        <div>
          <figure v-for="x in manyFoods">
            <img v-bind:src="x.url">
            <figcaption>{{ x.name }}</figcaption>
          </figure>
        </div>
      </div>
      
      <div id="app3">
        <form v-on:submit.prevent="addItem">
        <p>
              What do you need? <br>
        <input type="text" required placeholder="item name.." v-model="itemName">
        </p>
        <p>
              How many? <br>
        <input type="number" placeholder="number of items.." v-model="itemNumber">
        </p>
        <p>
              Important?
        <label>
        <input type="checkbox" v-model="itemImportant">
                {{ itemImportant }}
        </label>
        </p>
        <button type="submit">Add item</button>
        </form>
        <br>
        <hr>
         
          <div>
        <p><strong>Shopping list:</strong></p>
        <ul id="ulToFind">
        <li 
                v-for="item in shoppingList" 
                v-bind:class="{ impClass: item.important }"
                v-on:click="item.found=!item.found"
                v-show="!item.found">
                  {{ item.name }}, {{ item.number}}
        </li>
        </ul>
        <ul id="ulFound">
        <li 
                v-for="item in shoppingList" 
                v-bind:class="{ impClass: item.important }"
                v-on:click="item.found=!item.found"
                v-show="item.found">
                  {{ item.name }}, {{ item.number}}
        </li>
        </ul>
        </div>
</template>

<script></script>
<style></style>