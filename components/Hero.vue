<template>
  <div>
    <header
      class="page-hero"
      :style="{
        backgroundImage: `url(${'female-doctor-hospital-with-stethoscope.jpg'})`,
      }"
    >
      <v-container class="fill-height hero-container">
        <v-row align="center" class="fill-height">
          <h1 class="doctor-name white--text">
            {{$t('DoctorPage.DoctorName') }}
          </h1>
        </v-row>
      </v-container>
    </header>
  </div>
</template>

<style lang="scss">
.page-hero {
  width: 100%;
  height: 338px;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  position: relative;
  &::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    height: 100%;
    width: 100%;
    background: rgba(#000000, 0.5);
    z-index: 0;
  }.hero-container{
    position: relative;
  }
  .doctor-name {
    position: absolute;
    left: 12px;
  }
}
</style>
