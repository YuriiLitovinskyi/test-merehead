<template>
  <div id="app">
    <div id="nav">
      <div class="header">
        <router-link to="/">Home</router-link> |
        <router-link to="/about">About</router-link>        
      </div>      
    </div>
    <router-view/>
  </div>
</template>

<style>

*{        
  margin: 0;
  padding: 0;        
}

body {
  background-color: #f2f2f2;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;  
}

h2 {
  margin: 100px 0 20px;
}

table, th, td {
  border: 2px solid black;
  border-collapse: collapse;  
  margin: 0px auto;
  background-color: #e3e3e3;
}

@media screen and (max-width: 1500px) {
  table {
    width: 90%;    
    margin: auto;   
  }
}

th, td {
  padding: 15px;    
}

button {
  font-weight: bold; 
  font-size: 15px; 
  color: #303030;   
  padding: 5px 10px; 
  margin: 15px 2px;
  align-self: center;
  text-decoration: none;
  border-radius: 5px;
  box-shadow: 2.5px 2.5px #888888;
}

button:active {       
  background-color: #4C4CFF; 
}

button:hover:not(:active) { 
  background-color: #848484; 
  border-radius:5px; 
} 

.header {
  background: #333;
  color: #fff;
  text-align: center;
  padding: 20px;
}
.header a {
  color: #fff;
  padding-right: 5px;
  text-decoration: none;
} 

</style>
