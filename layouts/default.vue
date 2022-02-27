<template>
  <v-app>
    <AppBar />

    <v-main>
      <Nuxt />
    </v-main>

    <Footer />
    <Laoder />
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
}
</script>
<style lang="scss" >
body {
  margin-top: 64px;
  @include tablet {
    margin-top: 50px;
  }
}
</style>