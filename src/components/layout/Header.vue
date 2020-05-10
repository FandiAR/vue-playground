<template>
  <div class="container">
    <header>
      <a href="http://www.ponpesit.com/" class="logo">
        <img src="http://www.ponpesit.com/images/logo-DS.png" alt="Logo" />
      </a>
      <nav>
        <ul>
          <li>
            <router-link to="/">Todo List</router-link>
          </li>
          <li>
            <router-link to="/about">About</router-link>
          </li>
        </ul>
      </nav>
    </header>
  </div>
</template>

<script>
export default {
  name: "Header"
};
</script>

<style scoped>
.container {
  width: 100vw;
  margin: 0 auto;
  background: white;
}
header {
  width: 100vw;
  margin: auto;
  background: white;
  position: fixed;
  top: 0;
  z-index: 1;
  display: flex;
  align-items: center;
  box-shadow: 0 4px 5px -2px #72a065;
}
header a {
  text-decoration: none;
  user-select: none;
  color: #72a065;
}
header a.logo {
  padding: 0.5rem 0;
  font-weight: bold;
  padding-left: 5rem;
  padding-right: 20px;
}
header a.logo img {
  width: 30px;
}
header nav ul {
  list-style-type: none;
  display: flex;
}
.router-link-exact-active {
  border-bottom: solid 1px #72a065;
}
header nav ul a {
  padding: 0 1em;
}
/* header {
  background: #72a065;
  text-align: center;
  padding: 10px;
  display: flex;
}
header img {
  width: 50px;
}
header a {
  text-decoration: none;
}
h1 {
  color: white;
}
.header a {
  color: white;
  padding-right: 5px;
} */
</style>
