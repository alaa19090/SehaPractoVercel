<template>
  <div>
    <v-card
      height="110px"
      color="#f8f8f8"
      max-width="100%"
      class="rounded-0 justify-center align-center d-flex"
    >
      <v-card-title class="pa-0 font-weight-bold text-h5 primary--text mb-2">
        {{ $t('Aside.AppointmentBooking') }}
      </v-card-title>
    </v-card>

    <v-card
      class="rounded-lg py-md-8 px-md-6 py-4 px-3 mb-10"
      max-width="100%"
      style="margin-top: -5px"
    >
      <v-card-title class="pa-0">
        <h3 class="font-weight-bold subtitle-1 accent--text">
          {{ $t('Aside.DetectionType') }}
        </h3>
      </v-card-title>

      <v-checkbox
        color="primary"
        class="mt-2"
        hide-details="auto"
        :label="$t('Aside.OnlineDetection')"
      >
      </v-checkbox>
      <v-checkbox
        color="primary"
        class="mt-2"
        hide-details="auto"
        :label="$t('Aside.homeDetection')"
      >
      </v-checkbox>
      <v-checkbox
        color="primary"
        class="mt-2"
        hide-details="auto"
        :label="$t('Aside.Examination')"
      >
      </v-checkbox>

      <v-divider class="my-4"></v-divider>

      <v-card-title class="pa-0">
        <h3 class="font-weight-bold subtitle-1 accent--text">
          {{ $t('Aside.BookDoctor') }}
        </h3>
      </v-card-title>

      <!-- date-picker -->
      <v-dialog
        ref="dialog"
        v-model="modal"
        :return-value.sync="date"
        persistent
        width="290px"
      >
        <template v-slot:activator="{ on, attrs }">
          <v-card max-width="100px" class="rounded-0" elevation="0">
            <v-text-field
              :append-icon="!modal ? 'mdi-menu-down' : 'mdi-menu-up'"
              v-model="date"
              readonly
              v-bind="attrs"
              v-on="on"
              hide-details="auto"
            ></v-text-field>
          </v-card>
        </template>
        <v-date-picker
          show-adjacent-months
          v-model="date"
          type="month"
          scrollable
          :min="new Date().toISOString().substr(0, 7)"
          :locale="$vuetify.rtl ? 'ar' : 'en'"
        >
          <v-spacer></v-spacer>
          <v-btn text color="primary" @click="modal = false"> Cancel </v-btn>
          <v-btn text color="primary" @click="$refs.dialog.save(date)">
            OK
          </v-btn>
        </v-date-picker>
      </v-dialog>

      <br />
      <v-chip
        v-for="(link, index) in 12"
        :key="index"
        label
        class="ma-1 caption mr-0 px-1"
        :disabled="index === 2 || index === 4 || index === 7 || index === 8"
        outlined
      >
        {{ `${index + 1}.00 pm` }}
      </v-chip>

      <v-btn color="primary" class="my-2 rounded-lg" x-large block>{{$t('Aside.BookDoctor')}}</v-btn>
    </v-card>
  </div>
</template>

<script>
export default {
  data: () => ({
    date: new Date().toISOString().substr(0, 7),
    menu: false,
    modal: false,
  }),
}
</script>

<style lang="scss">
.v-input--is-label-active {
  label.theme--light.v-label {
    color: $primary !important;
    font-weight: bold;
  }
}
</style>