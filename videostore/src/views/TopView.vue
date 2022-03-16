<template>
  <div id="header">
    <div class="wrapper">
      <div class="products">
        <div class="info">
        <h1>Sly Cooper</h1>
        <p>Playstation</p>
        </div>
        <br>
        <div class="info">
        <h1>Fable</h1>
        <p>Xbox</p>
        </div>
        <br>
        <div class="info">
        <h1>Mario Kart</h1>
        <p>Nintendo</p>
        </div>
      </div>
    </div>
  </div>
</template>



<style scoped>
.info{
    margin: 10px;
}

.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.products {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.product {
  margin: 10px;
  margin-top: 50px;
  width: 200px;
}

.product img {
  border: 2px solid #333;
  height: 250px;
  width: 200px;
  object-fit: cover;
}

.product .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}

.info {
  border-radius: 25px;
  background: black;
  color: #000;
  padding: 10px 30px;
  height: 80px;
}

.info h1 {
  font-size: 16px;
  color: white;
}

.info h2 {
  font-size: 14px;
  color: white;
}

.info p {
  margin: 0px;
  color: white;
  font-size: 10px;
}

.price {
  display: flex;
  padding-top: 25px;
}

button {
  height: 50px;
  border-radius: 25px;
  background: #000;
  color: white;
  border: none;
}

.auto {
  margin-left: auto;
}
</style>