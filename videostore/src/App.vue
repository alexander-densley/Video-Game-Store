<template>
<div id="app">
  <div id="menu">
    <div id="brand">
      <router-link to="/">
        <img src="../images/xplanet.png">
      </router-link>
    </div>
    <div id="side">
      <router-link to="/browse">
        <div class="menu-item browse">
          <p>Browse</p>
        </div>
      </router-link>
      <router-link to="/cart">
        <div class="menu-item">
          <p>{{this.$root.$data.sumItems}} items</p>
        </div>
      </router-link>
      <router-link to="/top3">
        <div class = "menu-item top3">
          <p>Top 3</p>
        </div>
      </router-link>
    </div>
  </div>
  <router-view />
</div>
</template>


<script>
export default {
  name: 'storeCart',
  methods: {
    cartQuantity() {
      let cartQ = 0;
      for (let index in this.$root.$data.cart) {
        cartQ += this.$root.$data.cart[index].quantity;
      }
      return cartQ;
    }
  },
}
</script>



<style>

* {
  box-sizing: border-box;
}

body {
    background-color: grey;

  margin: 50px 100px;

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
  text-decoration: none;
}
.menu-item:hover{
  background-color: aliceblue;
  padding:10px;
}
.menu-item:visited, link {
  text-decoration: none;
}
p :visited, p:link, p:hover{
  text-decoration: none;
}


.menu-item p {
  margin: 0px;
  color: white;
}

.browse {
  margin-right: 50px;
}

.top3 {
  margin-left: 50px
}
</style>