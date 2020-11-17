<template>
<div id="app">
  <div id="menu">
    <div id="brand">
      <router-link to="/">
        Battaglia Mask Co.
      </router-link>
    </div>
    <div id="side">
      <router-link to="/browse">
        <div class="menu-item browse">
          <img src="/images/mask.png">
          <p>Browse</p>
        </div>
      </router-link>
      <router-link to="/faq">
        <div class="menu-item browse">
          <img src="/images/faq.png">
          <p>FAQ</p>
        </div>
      </router-link>
      <router-link to="/cart">
        <div class="menu-item">
          <img src="/images/cart.png">
          <p>{{cartLength}} items</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />
  <div class="footer">
    <a href="https://github.com/joelb97/creativeproject3">Github</a>
  </div>
</div>
</template>

<script>
export default {
  name: 'App',
  computed: {
    cartLength() {
      return this.$root.$data.cart.length;
    }
  }
}
</script>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 50px 100px;
  font-family: 'Anton', sans-serif;
}

a {
  text-decoration: none;
  color: black;
}

#menu {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-column-gap: 5px;
  grid-template-areas: "none brand side";
  margin-bottom: 50px;
}

#brand {
  grid-area: brand;
  display: flex;
  justify-content: center;
}

#brand a {
  font-size: 36px;
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
  align-items: center;
}

.menu-item p {
  margin: 0px;
}

.browse {
  margin-right: 50px;
}

.footer {
   position: fixed;
   left: 0;
   bottom: 0;
   width: 100%;
   text-align: center;
   background-color: #e3f2fd;
}
</style>
