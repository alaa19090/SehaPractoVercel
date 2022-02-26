<template>
  <section main>
    <v-card class="d-flex rounded-lg" max-width="100%">
      <v-img
        height="290"
        max-width="260"
        class="rounded-lg"
        src="/card-img.jpg"
      ></v-img>

      <div>
        <v-card-title
          ><h2 class="font-weight-light text-h5 accent--text">{{ $t('DoctorPage.DoctorName') }}</h2></v-card-title
        >

        <v-card-text>
          <v-row align="center" class="mx-0">
            <v-rating
              :value="4.5"
              color="amber"
              dense
              half-increments
              readonly
              size="14"
            ></v-rating>

            <div class="grey--text ms-4">4.5 (413)</div>
          </v-row>

          <div class="my-4 text-subtitle-1">$ • Italian, Cafe</div>

          <div>
            Small plates, salads & sandwiches - an intimate setting with 12
            indoor seats plus patio seating.
          </div>
        </v-card-text>
      </div>
    </v-card>
  </section>
</template>
<script>
export default {
  data() {
    return {}
  },
}
</script>
