<template>
  <v-overlay color="white" :value="showHideSpinner" opacity="0.95">
    <v-progress-circular indeterminate color="primary" size="64"></v-progress-circular>
  </v-overlay>
</template>
<script>
export default {
  beforeCreate() {
    this.showHideSpinner = true
  },
  mounted() {
    this.showHideSpinner = false
  },
  data() {
    return {
      showHideSpinner: true,
    }
  },
}
</script>