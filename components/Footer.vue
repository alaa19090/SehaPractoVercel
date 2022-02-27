<template>
  <footer>
    <v-card
      width="100%"
      height="400"
      elevation="0"
      class="footer-card rounded-0"
      color="primary"
    >
      <v-container class="py-md-15 py-10 px-md-0">
        <v-row justify="space-between" class="footer-row pt-md-10">
          <div>
            <nuxt-link to="/">
              <v-img src="/logo.png" max-width="130"></v-img>
            </nuxt-link>
            <div class="justify-space-around d-flex mx-md-0 mx-auto" style="width: 130px">
              <nuxt-link to="#">
                <v-icon color="white">mdi-facebook</v-icon>
              </nuxt-link>
              <nuxt-link to="#">
                <v-icon color="white">mdi-twitter</v-icon>
              </nuxt-link>
              <nuxt-link to="#">
                <v-icon color="white">mdi-instagram</v-icon>
              </nuxt-link>
            </div>
          </div>
          <div>
            <h4 class="text-h5 white--text mb-5 mt-10 mt-md-0">
              {{ $t('Footer.QuickLinks') }}
            </h4>
            <ul class="subtitle-1 white--text footer-list">
              <li class="mb-3">
                <nuxt-link class="white--text text-decoration-none" to="#">
                  {{ $t('Footer.TermsOfUse') }}</nuxt-link
                >
              </li>
              <li class="mb-3">
                <nuxt-link class="white--text text-decoration-none" to="#">
                  {{ $t('Footer.PrivacyPolicy') }}</nuxt-link
                >
              </li>
              <li class="mb-3">
                <nuxt-link class="white--text text-decoration-none" to="#">
                  {{ $t('Footer.who_are_we') }}</nuxt-link
                >
              </li>
              <li class="mb-3">
                <nuxt-link class="white--text text-decoration-none" to="#">
                  {{ $t('Footer.callUs') }}</nuxt-link
                >
              </li>
            </ul>
          </div>
          <div>
            <h4 class="text-h5 white--text mb-5 mt-10 mt-md-0">
              {{ $t('Footer.lockYourselFaway') }}
            </h4>
            <ul class="subtitle-1 white--text footer-list">
              <li class="mb-3">
                <nuxt-link class="white--text text-decoration-none" to="#">
                  {{ $t('Footer.Specialization') }}</nuxt-link
                >
              </li>
              <li class="mb-3">
                <nuxt-link class="white--text text-decoration-none" to="#">
                  {{ $t('Footer.Region') }}</nuxt-link
                >
              </li>
              <li class="mb-3">
                <nuxt-link class="white--text text-decoration-none" to="#">
                  {{ $t('Footer.theHospital') }}</nuxt-link
                >
              </li>
              <li class="mb-3">
                <nuxt-link class="white--text text-decoration-none" to="#">
                  {{ $t('Footer.MedicalCentersClinics') }}</nuxt-link
                >
              </li>
            </ul>
          </div>
          <div>
            <h4 class="text-h5 white--text mb-5 mt-10 mt-md-0">
              {{ $t('Footer.medicalStaff') }}
            </h4>
            <ul class="subtitle-1 white--text footer-list">
              <li class="mb-3">
                <nuxt-link class="white--text text-decoration-none" to="#">
                  {{ $t('Footer.JoinDoctor') }}</nuxt-link
                >
              </li>
              <li class="mb-3">
                <nuxt-link class="white--text text-decoration-none" to="#">
                  {{ $t('Footer.JoinNurse') }}</nuxt-link
                >
              </li>
              <li class="mb-3">
                <nuxt-link class="white--text text-decoration-none" to="#">
                  {{ $t('Footer.JoinMedicalCenter') }}</nuxt-link
                >
              </li>
              <li class="mb-3">
                <nuxt-link class="white--text text-decoration-none" to="#">
                  {{ $t('Footer.JoinPharmacy') }}</nuxt-link
                >
              </li>
            </ul>
          </div>
          <div>
            <h4 class="text-h5 white--text mb-5 mt-10 mt-md-0">
              {{ $t('Footer.Available') }}
            </h4>
            <v-btn
              to="/"
              class="text-capitalize mt-3"
              x-large
              width="75%"
              color="primary lighten-2"
            >
              <span class="mx-2"> google play</span>
              <v-icon size="35" color="white" class="mx-2">
                mdi-google-play</v-icon
              >
            </v-btn>
            <v-btn
              to="/"
              class="text-capitalize mt-3"
              x-large
              width="75%"
              color="primary lighten-2"
            >
              <span class="mx-2"> apple Store</span>
              <v-icon size="35" color="white" class="mx-2"> mdi-apple</v-icon>
            </v-btn>
          </div>
        </v-row>
      </v-container>
      <v-divider dark></v-divider>
    </v-card>
  </footer>
</template>
<style lang="scss">
.footer-row {
  height: 100%;
  > div {
    width: 20%;
    @include tablet {
      width: 100%;
    }
  }
}
.footer-list {
  list-style: none;
}
@include tablet {
  .footer-row {
    text-align: center;
  }
  .footer-card {
    height: auto !important;
  }
  .v-image {
    margin: auto;
  }
  .footer-list{
    padding: 0 !important;
    li.mb-3{
margin-bottom: 0px !important;
    }
  }
}
</style>