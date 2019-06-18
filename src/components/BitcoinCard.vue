<template>
  <div id="bitcoin-card">
    <ion-card v-for="item in this.data" :key="item.code">
      <ion-card-header>
        <ion-card-subtitle>{{ item.code }}</ion-card-subtitle>
        <ion-card-title>{{ item.rate_float }}</ion-card-title>
      </ion-card-header>
    </ion-card>
  </div>
</template>

<script>
export default {
  name: "BitcoinCard",
  props: {
    data: Array
  }
};
</script>
