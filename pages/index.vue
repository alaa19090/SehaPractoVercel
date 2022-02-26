<template>
  <div>
    <Hero />
    <v-container>
      <v-row>

        <!-- content column -->
        <v-col col="12" md="8">
          <Content />
        </v-col>

        <!-- sidbar column -->
        <v-col col="12" md="4">
          <!-- <Aside /> -->
        </v-col>

      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
}
</script>
