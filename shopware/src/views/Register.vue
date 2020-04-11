<template>
  <div id="register" class="vh-100 d-flex align-items-center mt-4">
    <div class="container my-5 py-5 ml-16 z-10">
      <!--Section: Content-->
      <section class="px-md-5 mx-md-5 text-center text-lg-left">
        <!--Grid row-->
        <div class="row d-flex justify-content-start">
          <!--Grid column-->
          <div class="col-md-6">
            <!-- Default form register -->
            <form class="text-center" v-on:submit.prevent="regSubmit">
              <p class="h4 mb-4 text-white">Registrera</p>

              <div class="form-row mb-4">
                <div class="col">
                  <input
                    type="text"
                    v-model="user.firstName"
                    class="form-control"
                    placeholder="Förnamn"
                  />
                </div>
                <div class="col">
                  <input
                    type="text"
                    v-model="user.lastName"
                    class="form-control"
                    placeholder="Efternamn"
                  />
                </div>
              </div>

              <input
                type="text"
                v-model="user.email"
                class="form-control mb-4"
                placeholder="E-mail"
              />

              <input
                type="password"
                v-model="user.password"
                class="form-control"
                placeholder="Lösenord"
              />

              <button class="btn btn-indigo my-4 btn-block" type="submit">Skapa nytt konto</button>
              <p>
                <span>Redan registrerad?</span>
                <router-link to="/login"> Logga in här</router-link>
              </p>
            </form>
            <!-- Default form register -->
          </div>
          <!--Grid column-->
        </div>
        <!--Grid row-->
      </section>
      <!--Section: Content-->
    </div>
  </div>
</template>

<script>
import { mapActions, mapState } from "vuex";
export default {
  data() {
    return {
      user: {
        firstName: "",
        lastName: "",
        email: "",
        password: ""
      }
    };
  },
  methods: {
    ...mapActions(["userRegister"]),
    regSubmit() {
      if (
        (this.user.firstName != "",
        this.user.lastName != "",
        this.user.email != "",
        this.user.password != "")
      ) {
        console.log("submit");
        this.userRegister(this.user);
      } else {
        console.log("Not valid");
      }
    }
  },
  created() {
    // this.userRegister(this.user)
    // this.$store.dispatch('userRegister')
  },
  computed: {
    // ...mapState(["status"])
  }
};
</script>

<style scoped>
#register{
  background-color: rgb(29, 29, 29);
  color: white;
}
#register:after{
  position: absolute;
  content: '';
  top: 0;
  right: 0;
  left: 0;
  bottom: 0;
  background-image: url('../assets/shopware.png');
  background-position: center;
  background-size: cover;
}
.ml-16{
  margin-left: 13em;
}
.z-10{
  z-index: 10;
}
</style>