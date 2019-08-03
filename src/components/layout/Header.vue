<template>
    <header class="header">
        <h1>Drawing</h1>
        <ul id="nav">
          <li><router-link to="/">Home</router-link></li>
          <li><router-link to="/upload">Upload files</router-link></li>
          <li><router-link to="/search">Search</router-link></li>
          <li><router-link to="/about">About</router-link></li>
        </ul>
    </header>
</template>

<script>
export default {
    name: "Header"
}
</script>

<style scoped>
  .header {
    background-color: #92b0b3;
    margin-bottom: 20px;
    text-align: center;
    padding: 10px;
  }

  .header li {
    display: inline;
    list-style: none;
    padding: 0 10px;
  }

  .header li + li {
    border-left: 1px solid #fff;
  }

  .header li a {
    color: #fff;
    text-decoration: none;
  }
</style>
