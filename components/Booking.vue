<template>
  <v-card
    style="margin-top: -90px"
    width="100%"
    class="
      d-flex
      justify-space-between
      py-9
      px-6
      primary
      rounded-xl
      mb-13
      filter-card
    "
  >
    <v-select
      :items="items"
      :label="$t('Booking.ChooseSpecialty')"
      prepend-inner-icon="mdi-stethoscope"
      solo
      class="rounded-lg mx-2"
      hide-details="auto"
      height="60"
    ></v-select>
    <v-select
      :items="items"
      :label="$t('Booking.ChooseProvince')"
      prepend-inner-icon="mdi-map-marker-outline"
      solo
      class="rounded-lg mx-2"
      hide-details="auto"
      height="60"
    ></v-select>
    <v-select
      :items="items"
      :label="$t('Booking.ChooseRegion')"
      prepend-inner-icon="mdi-map-marker-outline"
      solo
      class="rounded-lg mx-2"
      hide-details="auto"
      height="60"
    ></v-select>

    <v-select
      :items="items"
      :label="$t('Booking.ChooseInsurance')"
      prepend-inner-icon="mdi-umbrella-outline"
      solo
      class="rounded-lg mx-2"
      hide-details="auto"
      height="60"
    ></v-select>

    <v-btn
      x-large
      class="rounded-lg mx-2 white--text filter-btn"
      color="secondary"
      height="60"
      width="17%"
    >
      <v-icon color="white" class="mx-1" size="30">mdi-magnify</v-icon>
      <span sclass="mx-1">{{ $t('Booking.Search') }}</span>
    </v-btn>
  </v-card>
</template>
<script>
export default {
  data: () => ({
    items: ['Foo', 'Bar', 'Fizz', 'Buzz'],
  }),
}
</script>
<style lang="scss">
.filter-card {
  @include tablet {
    flex-direction: column;
  }
  @include tablet {
    .filter-btn {
      width: 100% !important;
      margin: auto !important;
    }
    .v-select {
      width: 100% !important;
      margin: auto !important;
      margin-bottom: 12px !important;

    }
  }
}
</style>