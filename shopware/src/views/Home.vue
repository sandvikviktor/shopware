<template>
  <div id="home" class="d-flex vh-100 w-100 align-items-center">
   <div class="jumbo">
      <h1>Shopware e-commerce</h1>
      <p class="lead ml-1">Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorum architecto vel rem ullam dolore voluptate fuga nam!</p>
      <!-- <a class="btn btn-indigo btn-lg" href="#" role="button">Get Started</a> -->
      <router-link to="/register" type="button" class="btn btn-indigo btn-lg px-5">Skapa konto</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "Home",
}
</script>

<style scoped>
#home{
  background-color: rgb(29, 29, 29);
  color: white;
}
#home:before{
  position: fixed;
  content: '';
  top: 0;
  right: 0;
  left: 0;
  bottom: 0;
  background-image: url('../assets/shopware.png');
  background-position: center;
  background-size: cover;
}
hr{
  width: 90%;
}
h1{
  font-size: 3.5rem;
}
.jumbo{
  z-index: 10;
  margin-top: 3em;
  margin-left: 13em;
}
p{
  max-width: 35em;
}

/* Laptops */
@media (max-height: 768px), (min-width: 900px) {
  #home:after {
    transform: scale(0.9);
    right: -7em;
    bottom: -5em;
  }
  .jumbo{
    margin-left: 10em;
  }
  h1{
    font-size: 3rem;
  }
  p{
    font-size: 1.1rem;
  }
}
@media (max-width: 578px) {
    #home:after {
    transform: scale(0.6);
    left: -40em;
    right: -18em;
    bottom: -14em;
  }
  /* #home:after{
  content: '';
  z-index: 9;
  background-color: rgba(0, 0, 0, 0.726);
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  transform: scale(1);
} */
  .jumbo{
    margin: 0;
    padding: 0 1em;
  }
  h1 {
    font-size: 2rem;
  }
  p{
    font-size: 0.9rem;
  }
}
</style>