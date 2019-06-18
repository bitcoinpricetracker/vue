<template>
  <ion-app>
    <ion-header>
      <ion-toolbar color="primary">
        <ion-title>Bitcoin Price Tracker</ion-title>
      </ion-toolbar>
    </ion-header>
    <ion-content>
      <section class="bitcoin__header">
        <ion-icon name="logo-bitcoin" class="bitcoin__logo"></ion-icon>
      </section>
      <template v-if="loading">
        <loading-card />
        <loading-card />
        <loading-card />
      </template>
      <template v-else>
        <bitcoin-card :data="bitcoinData" />
      </template>
    </ion-content>
  </ion-app>
</template>

<script>
import LoadingCard from "./components/LoadingCard";
import BitcoinCard from "./components/BitcoinCard";
import { getBitcoinPrice } from "./api/Bitcoin";
export default {
  components: {
    LoadingCard,
    BitcoinCard
  },
  async mounted() {
    this.result = await getBitcoinPrice();
    this.loading = false;
  },
  data() {
    return {
      loading: true,
      result: {}
    };
  },
  computed: {
    bitcoinData() {
      return Object.keys(this.result.bpi || {}).map(
        item => this.result.bpi[item]
      );
    }
  }
};
</script>

<style lang="scss">
.bitcoin__logo {
  width: 140px;
  height: 140px;
  display: block;
  margin: 0 auto;
  color: white;
}
.bitcoin__header {
  background-color: #29308f;
}
ion-content {
  --background: #3b43be;
}
ion-card {
  --background: white !important;
}
</style>
