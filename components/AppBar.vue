<template>
  <nav>
    <v-app-bar
      fixed
      flat
      color="white"
      class="nav-bar"
      :min-height="$vuetify.breakpoint.mdAndUp ? '64' : '50'"
      elevation="2"
    >
      <div class="d-flex align-center" v-if="$vuetify.breakpoint.mdAndUp">
        <nuxt-link to="/">
          <v-img src="/logo.png" max-width="50px" class="mr-4 logo"></v-img>
        </nuxt-link>

        <nuxt-link
          to="#"
          class="
            mx-8
            subtitle-2
            font-weight-bold
            black--text
            text-decoration-none
          "
          >{{ $t('Nav.Home') }}</nuxt-link
        >
        <nuxt-link
          to="/"
          class="
            mx-8
            subtitle-2
            font-weight-bold
            black--text
            text-decoration-none
          "
          >{{ $t('Nav.AboutUs') }}</nuxt-link
        >
        <nuxt-link
          to="#"
          class="
            mx-8
            subtitle-2
            font-weight-bold
            black--text
            text-decoration-none
          "
          >{{ $t('Nav.MedicalStaff') }}</nuxt-link
        >
        <nuxt-link
          to="#"
          class="
            mx-8
            subtitle-2
            font-weight-bold
            black--text
            text-decoration-none
          "
          >{{ $t('Nav.ContactUs') }}</nuxt-link
        >
      </div>
      <v-spacer v-if="$vuetify.breakpoint.mdAndUp"></v-spacer>

      <!-- hide on pc -->
      <v-btn icon v-if="!$vuetify.breakpoint.mdAndUp" @click="drawer = !drawer">
        <v-icon color="black">mdi-menu</v-icon>
      </v-btn>

      <v-btn icon :small="!$vuetify.breakpoint.mdAndUp">
        <v-badge left color="secondary" bordered dot overlap>
          <v-icon color="black">mdi-cart-outline</v-icon>
        </v-badge>
      </v-btn>

      <v-spacer></v-spacer>

      <nuxt-link to="/">
        <v-img src="/logo.png" max-width="50px" class="mr-4 logo"></v-img>
        <!-- hide on pc -->
      </nuxt-link>
      <v-spacer v-if="!$vuetify.breakpoint.mdAndUp"></v-spacer>
      <!-- hide on pc -->

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
            class="text-uppercase caption mx-md-2"
          >
            <v-img width="25px" :src="`${lang}.jpg`" class="mx-md-1"> </v-img>
            {{ $vuetify.breakpoint.mdAndUp ? $t(`Nav.${lang}`) : '' }}
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
        v-if="$vuetify.breakpoint.mdAndUp"
        color="primary"
        min-width="142"
        dark
        class="caption rounded-lg px-8 py-5"
        >{{ $t('Nav.Login') }}</v-btn
      >
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" fixed :right="$vuetify.rtl">
      <v-list-item>
        <v-list-item-avatar @click="drawer = !drawer">
          <v-icon color="black">mdi-close</v-icon>
        </v-list-item-avatar>
      </v-list-item>

      <v-divider></v-divider>

      <v-list dense>
        <v-list-item link>
          <v-list-item-content>
            <v-list-item-title>{{ $t('Nav.Home') }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link>
          <v-list-item-content>
            <v-list-item-title>{{ $t('Nav.AboutUs') }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link>
          <v-list-item-content>
            <v-list-item-title>{{ $t('Nav.MedicalStaff') }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link>
          <v-list-item-content>
            <v-list-item-title>{{ $t('Nav.ContactUs') }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
        <v-list-item link>
          <v-list-item-content>
            <v-list-item-title>{{ $t('Nav.Login') }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
      <v-spacer></v-spacer>
      <nuxt-link to="/" class="logo-nav">
        <v-img src="/logo.png" class="mx-auto" max-width="130"></v-img>
      </nuxt-link>
    </v-navigation-drawer>
  </nav>
</template>
<script>
export default {
  name: 'DefaultLayout',
  data() {
    return {
      lang: 'en',
      menu: false,
      drawer: false,
      language: this.$i18n.localeCodes || [],
    }
  },
  mounted() {
    this.language = this.$i18n.localeCodes

    //check if there any cookeis in borwser
    const i18n_redirected = this.getCookie('i18n_redirected')
    if (i18n_redirected) {
      this.lang = i18n_redirected
      if (this.lang == 'ar') {
        this.$vuetify.rtl = true
      } else {
        this.$vuetify.rtl = false
      }
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
      letter-spacing: 0 !important;
    } //all arabic text
    .mr-4.logo {
      margin-right: 0 !important;
      margin-left: 16px;
    }
    .pr-5.content-section {
      padding-right: 0 !important;
      padding-left: 20px !important;
      @include tablet {
        padding: 0 !important;
      }
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
.logo-nav {
  position: absolute;
  bottom: 25px;
  left: 0;
  right: 0;
}
</style>
