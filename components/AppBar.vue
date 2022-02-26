<template>
  <nav>
    <v-toolbar
      app
      flat
      fixed
      color="white"
      class="nav-bar"
      max-height="64"
      elevation="0"
    >
      <v-toolbar-items class="align-center">
        <nuxt-link to="/">
          <v-img src="/logo.jpg" max-width="35px" class="mr-4 logo"></v-img>
        </nuxt-link>

        <nuxt-link
          to="#"
          class="mx-8 subtitle-2 font-weight-bold black--text text-decoration-none"
          >{{ $t('Nav.Home') }}</nuxt-link
        >
        <nuxt-link
          to="/"
          class="mx-8 subtitle-2 font-weight-bold black--text text-decoration-none"
          >{{ $t('Nav.AboutUs') }}</nuxt-link
        >
        <nuxt-link
          to="#"
          class="mx-8 subtitle-2 font-weight-bold black--text text-decoration-none"
          >{{ $t('Nav.MedicalStaff') }}</nuxt-link
        >
        <nuxt-link
          to="#"
          class="mx-8 subtitle-2 font-weight-bold black--text text-decoration-none"
          >{{ $t('Nav.ContactUs') }}</nuxt-link
        >
      </v-toolbar-items>
      <v-spacer></v-spacer>
      <v-btn icon>
        <v-badge left color="secondary" bordered dot overlap>
          <v-icon color="black">mdi-cart-outline</v-icon>
        </v-badge>
      </v-btn>

      <v-menu
        v-model="menu"
        dense
        open-on-hover
        bottom
        offset-y
        content-class="language-menu"
      >
        <template v-slot:activator="{ on, attrs }">
          <v-btn
            text
            color="black"
            small
            dark
            v-bind="attrs"
            v-on="on"
            class="text-uppercase caption mx-2"
          >
            <v-img width="25px" :src="`${lang}.jpg`" class="mx-1"> </v-img>
            {{ $t(`Nav.${lang}`) }}
            <v-icon size="15" color="black">{{
              !menu ? 'mdi-menu-down' : 'mdi-menu-up'
            }}</v-icon>
          </v-btn>
        </template>

        <v-list dense>
          <v-list-item
            dense
            v-for="(item, index) in language"
            :key="index"
            @click="languageSwitch(item)"
          >
            <v-list-item-title class="text-uppercase">{{
              $t(`Nav.${item}`)
            }}</v-list-item-title>
            <v-list-item-action>
              <v-img width="25px" :src="`${item}.jpg`" class="mx-1"> </v-img>
            </v-list-item-action>
          </v-list-item>
        </v-list>
      </v-menu>

      <v-btn
        color="primary"
        min-width="142"
        dark
        class="caption rounded-lg px-8 py-5"
        >{{ $t('Nav.Login') }}</v-btn
      >
    </v-toolbar>
  </nav>
</template>
<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      lang: '',
      menu: false,
      language: this.$i18n.localeCodes || [],
    }
  },
  mounted() {
    this.language = this.$i18n.localeCodes

    //check if there any cookeis in borwser
    const i18n_redirected = this.getCookie('i18n_redirected')
    if (i18n_redirected) {
      this.lang = i18n_redirected
    } else {
      this.lang = this.$i18n.defaultLocale
    }
  },
  head() {
    return {
      htmlAttrs: {
        lang: this.lang,
      },
    }
  },
  methods: {
    languageSwitch(val) {
      this.$i18n.setLocale(val)
      this.lang = val

      if (val == 'ar') {
        this.$vuetify.rtl = true
      } else {
        this.$vuetify.rtl = false
      }
    },
    getCookie(name) {
      var match = document.cookie.match(new RegExp('(^| )' + name + '=([^;]+)'))
      if (match) {
        return match[2]
      } else {
        console.log('--something went wrong---')
      }
    },
  },
}
</script>
<style lang="scss">
html[lang='ar'] {
  .v-application {
    * {
      font-family: 'Almarai', sans-serif !important;
    } //all arabic text
    .mr-4.logo {
      margin-right: 0 !important;
      margin-left: 16px;
    }
  }
}
.nav-bar {
  .v-toolbar__content {
    width: 100%;
    padding: 12px;
    margin-right: auto;
    margin-left: auto;
  }
  @media (min-width: 960px) {
    .v-toolbar__content {
      max-width: 900px;
    }
  }
  @media (min-width: 1264px) {
    .v-toolbar__content {
      max-width: 1185px;
    }
  }
  @media (min-width: 1904px) {
    .v-toolbar__content {
      max-width: 1785px;
    }
  }
}
</style>
