<template>
  <v-app>
    <AppBar />

    <v-main>
      <Nuxt />
    </v-main>
    
    <Footer />
  </v-app>
</template>

<script>
export default {
  name: 'DefaultLayout',
}
</script>
<style >
body {
  margin-top: 64px;
}
</style>