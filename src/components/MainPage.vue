<template>
  <div class="MainPage">
    <div class="nav">
      <NavBar />
    </div>
    <div class="orchard">
      <OrchardCanvas />
    </div>
    <div class="spendingCard" v-if="getSpendings">
      <SpendingsCard />
    </div>
    <div class="savingsCard" v-if="getSavings">
      <SavingsCard />
    </div>
  </div>
</template>

<script>
import OrchardCanvas from "./OrchardCanvas.vue";
import NavBar from "./NavBar";
import SavingsCard from "./SavingsCard.vue";
import SpendingsCard from "./SpendingsCard.vue";
import { mapGetters } from "vuex";

export default {
  name: "MainPage",
  components: {
    OrchardCanvas,
    NavBar,
    SavingsCard,
    SpendingsCard
  },
  computed: {
    ...mapGetters(["getSavingGoals", "getSpendings", "getSavings"]),

    showGoal: function() {
      return this.getSavingGoals;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.MainPage {
  display: flex;
}
.orchard {
  width: 50%;
  padding-left: 2rem;
  padding-right: 6.75rem;
  overflow: hidden;
  margin-top: 3rem;
}

.savingsCard {
  width: 50%;
  padding-right: 7rem;
  margin-top: 3rem;
}
</style>
