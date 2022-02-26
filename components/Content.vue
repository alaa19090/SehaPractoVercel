<template>
  <section class="pr-5 content-section">
    <!-- first card  -->
    <v-card class="d-flex rounded-lg first-card" max-width="100%">
      <v-img
        height="290"
        max-width="260"
        class="rounded-lg"
        src="/card-img.jpg"
      ></v-img>

      <div>
        <v-card-title class="pb-0"
          ><h2 class="font-weight-light text-h5 accent--text mb-3">
            {{ $t('DoctorPage.DoctorName') }}
          </h2></v-card-title
        >

        <v-card-text>
          <p class="grey--text subtitle-2">
            {{ $t('DoctorPage.DoctorDescription') }}
          </p>
          <v-row align="center" class="mx-0 mt-3 mb-5">
            <v-rating
              :value="4"
              color="amber"
              dense
              half-increments
              readonly
              size="20"
            ></v-rating>

            <span class="grey--text ms-4 caption"
              >85 {{ $t('DoctorPage.rating') }}</span
            >
          </v-row>
          <v-divider class="my-2"></v-divider>
          <p class="mb-2">
            <v-icon size="18" color="gary" class="mx-1"
              >mdi-map-marker-outline</v-icon
            ><span class="caption black--text">{{
              $t('DoctorPage.location')
            }}</span>
          </p>

          <p class="mb-2">
            <v-icon size="18" color="gary" class="mx-1"
              >mdi-timer-outline</v-icon
            ><span class="grey--text caption"
              >{{ $t('DoctorPage.WorkingHours') }} :
              <span class="black--text">{{
                $t('DoctorPage.WorkingHoursVal')
              }}</span></span
            >
          </p>

          <p class="mb-2">
            <v-icon size="18" color="gary" class="mx-1"
              >mdi-clock-outline</v-icon
            ><span class="grey--text caption"
              >{{ $t('DoctorPage.WaitingTime') }} :
              <span class="black--text">{{
                $t('DoctorPage.WaitingTimeVal')
              }}</span></span
            >
          </p>

          <p class="mb-2">
            <v-icon size="18" color="gary" class="mx-1"
              >mdi-wallet-outline</v-icon
            ><span class="grey--text caption"
              >{{ $t('DoctorPage.Price') }} :
              <span class="black--text">{{
                $t('DoctorPage.PriceVal')
              }}</span></span
            >
          </p>
        </v-card-text>
      </div>
    </v-card>

    <!-- taggel section -->
    <v-btn-toggle
      color="primary"
      class="toggle-exclusive my-10"
      v-model="toggle_exclusive"
    >
      <v-btn height="85" x-large class="font-weight-bold subtitle-1">
        {{ $t('DoctorPage.AboutDoctor') }}
      </v-btn>
      <v-btn height="85" x-large class="font-weight-bold subtitle-1">
        {{ $t('DoctorPage.rating') }}
      </v-btn>
    </v-btn-toggle>

    <!-- About Doctor section -->
    <div class="about-doctor" v-if="!toggle_exclusive">
      <!-- 1 InfoAboutDoctor-->
      <v-card class="rounded-lg py-8 px-6 mb-10" max-width="100%">
        <v-card-title class="pa-0">
          <h2 class="font-weight-bold text-h5 accent--text mb-3">
            <v-icon color="primary" size="30">mdi-information-outline</v-icon>
            <span class="mx-1">{{ $t('DoctorPage.InfoAboutDoctor') }}</span>
          </h2>
        </v-card-title>

        <v-card-text>
          <p class="grey--text subtitle-2 mb-0">
            {{ $t('DoctorPage.TestText') }}
          </p>
        </v-card-text>
      </v-card>

      <!-- 2 workplace -->
      <v-card class="rounded-lg py-8 px-6 mb-10" max-width="100%">
        <v-card-title class="pa-0">
          <h2 class="font-weight-bold text-h5 accent--text mb-4">
            <v-icon class="mb-2" color="primary" size="30">mdi-medical-bag</v-icon>
            <span class="mx-1">{{ $t('DoctorPage.Workplace') }}</span>
          </h2>
        </v-card-title>

        <v-card-text>
          <v-row>
            <v-col cols="12" md="6" class="pa-0">
              <p class="mb-2">
                <span class="accent--text subtitle-1 font-weight-bold mx-2">
                  {{ $t('DoctorPage.locationTilte1') }}
                </span>
                <br />
                <v-icon size="18" color="gary" class="mx-1"
                  >mdi-map-marker-outline</v-icon
                >
                <span class="caption gary--text">
                  {{ $t('DoctorPage.location') }}
                </span>
                <br />
                <v-icon size="18" color="gary" class="mx-1"
                  >mdi-phone-outline</v-icon
                >
                <span class="caption gary--text"> 05645878745 </span>
              </p>
            </v-col>
            <v-col cols="12" md="6" class="pa-0">
              <p class="mb-2">
                <span class="accent--text subtitle-1 font-weight-bold mx-2">
                  {{ $t('DoctorPage.locationTilte2') }}
                </span>
                <br />
                <v-icon size="18" color="gary" class="mx-1"
                  >mdi-map-marker-outline</v-icon
                >
                <span class="caption gary--text">
                  {{ $t('DoctorPage.location') }}
                </span>
              </p>
            </v-col>
            <v-col cols="12" md="6" class="pa-0">
              <p class="mb-2">
                <span class="accent--text subtitle-1 font-weight-bold mx-2">
                  {{ $t('DoctorPage.locationTilte3') }}
                </span>
                <br />
                <v-icon size="18" color="gary" class="mx-1"
                  >mdi-map-marker-outline</v-icon
                >
                <span class="caption gary--text">
                  {{ $t('DoctorPage.location') }}
                </span>
              </p>
            </v-col>
            <v-col cols="12" md="6" class="pa-0">
              <p class="mb-2">
                <span class="accent--text subtitle-1 font-weight-bold mx-2">
                  {{ $t('DoctorPage.locationTilte4') }}
                </span>
                <br />
                <v-icon size="18" color="gary" class="mx-1"
                  >mdi-map-marker-outline</v-icon
                >
                <span class="caption gary--text">
                  {{ $t('DoctorPage.location') }}
                </span>
                <br />
                <v-icon size="18" color="gary" class="mx-1"
                  >mdi-phone-outline</v-icon
                >
                <span class="caption gary--text"> 05645878745 </span>
              </p>
            </v-col>
          </v-row>
        </v-card-text>
      </v-card>

      <!-- 3 medical services -->
      <v-card class="rounded-lg pt-8 pb-4 px-6 mb-10" max-width="100%">
        <v-card-title class="pa-0">
          <h2 class="font-weight-bold text-h5 accent--text mb-3">
            <v-icon color="primary" size="30">mdi-stethoscope</v-icon>
            <span class="mx-1">{{ $t('DoctorPage.MedicalServices') }}</span>
          </h2>
        </v-card-title>

        <v-card-text>
          <v-chip
            v-for="(link, index) in 6"
            :key="index"
            label
            link
            class="mr-3 mb-3 font-weight-bold subtitle-1 accent--text pa-6"
            color="#f1f1f1"
            to="#"
          >
            {{ $t(`DoctorPage.MedicalServices${index + 1}`) }}
          </v-chip>
        </v-card-text>
      </v-card>

      <!-- 4 certificate -->
      <v-card class="rounded-lg pt-8 pb-4 px-6 mb-10" max-width="100%">
        <v-card-title class="pa-0">
          <h2 class="font-weight-bold text-h5 accent--text mb-3">
            <v-icon color="primary" size="30">mdi-certificate</v-icon>
            <span class="mx-1">{{ $t('DoctorPage.MedicalServices') }}</span>
          </h2>
        </v-card-title>

        <v-card-text class="d-flex flex-wrap">
          <v-img
            :src="`/certificate/${index + 1}.png`"
            class="rounded img-border mr-3 mb-3"
            max-width="150px"
            height="100px"
            v-for="(link, index) in 6"
            :key="index"
          ></v-img>
        </v-card-text>
      </v-card>

      <!-- 4 Instructions for patients -->
      <v-card class="rounded-lg pt-8 pb-4 px-6 mb-10" max-width="100%">
        <v-card-title class="pa-0">
          <h2 class="font-weight-bold text-h5 accent--text mb-3">
            <v-icon color="primary" size="30">mdi-comment-text-outline</v-icon>
            <span class="mx-1">{{
              $t('DoctorPage.InstructionsForPatients')
            }}</span>
          </h2>
        </v-card-title>

        <v-card-text class="d-flex flex-wrap instructions-wrap">
          <span class="accent--text subtitle-1 font-weight-bold mb-2">
            {{ $t('DoctorPage.Instructions1') }}
          </span>
          <span class="accent--text subtitle-1 font-weight-bold mb-2">
            {{ $t('DoctorPage.Instructions2') }}
          </span>
          <span class="accent--text subtitle-1 font-weight-bold mb-2">
            {{ $t('DoctorPage.Instructions3') }}
          </span>
          <span class="accent--text subtitle-1 font-weight-bold mb-2">
            {{ $t('DoctorPage.Instructions4') }}
          </span>
        </v-card-text>
      </v-card>

    </div>

    <!-- Rating section -->
    <div class="rating-doctor" v-else></div>
  </section>
</template>
<script>
export default {
  data() {
    return {
      toggle_exclusive: 0, //on select button of button group is return the index of button
    }
  },
}
</script>
<style lang="scss">
.toggle-exclusive {
  width: 100%;
  button {
    width: 50%;
  }
}
.img-border {
  border: 3px solid #3e4595;
}
.instructions-wrap {
  span {
    width: 48%;
    @include tablet {
      width:100%;

    }
  }
}
</style>