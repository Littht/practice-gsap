<template>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link to='/contact' >Contact</router-link>
  </nav>
  <router-view/>
</template>

<style>
*{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #2b2b2b;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}

nav{
  display:flex;
  height: 80px;
  justify-content: center;
  background-color: #737373;
  align-items: center;
  gap: 1em;
  margin-bottom: 50px;
}

body{
  background: #f4f4f4;
}
</style>
