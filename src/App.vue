<template>
<div id="app">
  <!-- <div id="menu">
    <div id="brand">
      <router-link to="/">
        <img src="/images/logo.png">
      </router-link>
    </div>
    <div id="side">
      <router-link to="/browse">
        <div class="menu-item browse">
          <img src="/images/globe.png">
          <p>Browse</p>
        </div>
      </router-link>
      <router-link to="/cart">
        <div class="menu-item">
          <img src="/images/love.png">
          <p>{{cartSizeString}}</p>
        </div>
      </router-link>
    </div>
  </div> -->
  <div class="container mt-3">
    <router-view />
  </div>
  <footer class="text-center fixed-bottom bg-light">
    <div class="text-center p-1">
      <a class="text-muted stretched-link" target="_blank" rel="noopener noreferrer" href="https://github.com/jacob-hart/dark-directory"><small>Source</small></a>
    </div>
  </footer>
</div>
</template>

<script>
export default {
  name: 'App',
}
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  /*background-color: black;*/
}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  margin-bottom: 50px;
}

#menu a {
  color: #B84901;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand img {
  height: 200px;
}

#side {
  grid-area: side;
  display: flex;
  justify-content: flex-end;
}

#side img {
  width: 50px;
}

.menu-item {
  display: flex;
  flex-direction: column;
}

.menu-item p {
  margin: 0px;
}

.browse {
  margin-right: 50px;
}
</style>

