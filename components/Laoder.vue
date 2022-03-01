<template>
  <v-overlay color="white" :value="showHideSpinner" opacity="0.95">
    <v-progress-circular
      indeterminate
      color="primary"
      size="64"
    ></v-progress-circular>
  </v-overlay>
</template>
<script>
export default {
  mounted() {
    this.$nextTick(() => {
      setTimeout(() => (this.showHideSpinner = false), 500)
    })
  },

  beforeCreate() {
    this.showHideSpinner = true
  },
  data() {
    return {
      showHideSpinner: true,
    }
  },
}
</script>