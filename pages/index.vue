<template>
  <div>
    <Hero />
    <v-container>
      <v-row>
        <!-- content column -->
        <v-col cols="12" md="8">
          <Content />
        </v-col>

        <!-- sidbar column -->
        <v-col cols="12" md="4">
          <aside>
            <Aside />
          </aside>
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
