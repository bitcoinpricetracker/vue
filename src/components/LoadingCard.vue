<template>
  <ion-card>
    <ion-card-header>
      <ion-card-subtitle>
        <ion-skeleton-text class="loading-card__currency-value" animated />
      </ion-card-subtitle>
      <ion-card-title>
        <ion-skeleton-text class="loading-card__currency-name" animated />
      </ion-card-title>
    </ion-card-header>
  </ion-card>
</template>

<script>
export default {
  name: "LoadingCard"
};
</script>

<style scoped lang="scss">
.loading-card__currency-name {
  width: 50px;
}
.loading-card__currency-value {
  width: 150px;
  height: 30px;
}
</style>
