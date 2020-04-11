<template>
  <div id="manage" v-if="getSavedOrders" class="vh-100 w-100 pt-5 container-fluid">
    <!-- <div class="col-7"></div> -->
    <!-- <div class="vh-50 w-100">hej</div> -->
    <div class="container mt-5 rounded px-0 position-relative z-10">
        <!-- Shopping Cart table -->
        <div class="table-responsive z-depth-0">
            <!-- Sparade Ordrar -->
            <OrderProduct v-for="order in getSavedOrders" :key="order._id" :order="order" />
        </div>
    </div>
  </div>
</template>

<script>
import OrderProduct from "@/components/order/OrderProductSaved";
import { mapActions, mapGetters } from "vuex";
export default {
  name: "Manage",
  components: {
    OrderProduct
  },
  methods: {
    ...mapActions(["getOrdersById"])
  },
  created() {
    this.getOrdersById(this.currentUserId);
  },
  computed: {
    ...mapGetters(["getSavedOrders", "currentUserId"])
  }
};
</script>

<style scoped>
/* #manage{
  min-height: 100vh;
} */
#manage{
  background-color: rgb(27, 27, 27);
}
#manage:before{
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
#manage:after{
  content: '';
  height: 100%;
  z-index: 9;
  background-color: rgba(0, 0, 0, 0.726);
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
}
.z-10{
  z-index: 10;
}
</style>