<template>
  <v-app>
    <v-app-bar app elevation="0" class="app white">
      <v-dialog
        v-model="dialog"
        fullscreen
        hide-overlay
        transition="dialog-bottom-transition"
      >
        <template v-slot:activator="{ on }">
          <v-btn icon v-on="on" class="hidden-md-and-up mr-0">
            <v-icon class="secondary--text">fas fa-bars</v-icon>
          </v-btn>
        </template>
        <v-card>
          <v-toolbar class="mont">
            <v-toolbar-title class="mont secondary--text">{{
              $static.metadata.siteName
            }}</v-toolbar-title>
            <v-spacer></v-spacer>
            <v-btn
              icon
              class="secondary--text"
              style="font-size: 1.7em;"
              @click="dialog = false"
              >X</v-btn
            >
          </v-toolbar>
          <v-container fluid ma-0 pa-0 style="min-height: 100vh;">
            <v-row justify="center" py-6>
              <v-col cols="12" class="text-center">
                <g-link to="/">
                  <p class="secondary--text display-1 mt-4">Home</p>
                </g-link>
              </v-col>
              <v-col cols="12" class="text-center">
                <g-link to="/store">
                  <p class="secondary--text display-1 mt-4">Store</p>
                </g-link>
              </v-col>
              <v-col cols="12" class="text-center">
                <g-link to="/about">
                  <p class="secondary--text display-1 mt-4">About</p>
                </g-link>
              </v-col>
              <v-col cols="12" class="text-center">
                <g-link to="/blog">
                  <p class="secondary--text display-1 mt-4">Blog</p>
                </g-link>
              </v-col>
              <v-col cols="12" class="text-center">
                <g-link to="/contact">
                  <p class="secondary--text display-1 mt-4">Contact</p>
                </g-link>
              </v-col>
            </v-row>
          </v-container>
        </v-card>
      </v-dialog>
      <v-container>
        <v-row class="align-center">
          <v-col class="text-center text-md-left">
            <g-link to="/">
              <v-toolbar-title
                class="secondary--text mont"
                style="font-size: 1.8em;"
                >{{ $static.metadata.siteName }}</v-toolbar-title
              >
            </g-link>
          </v-col>
          <!-- NAVBAR FOR bold AND UP SCREEN SIZES -->
          <v-toolbar-items class="hidden-sm-and-down">
            <v-btn text to="/" class="no-active">
              <span class="nav-text secondary--text py-2">Home</span>
            </v-btn>
            <v-btn text to="/store" class="no-active">
              <span class="nav-text secondary--text py-2">Store</span>
            </v-btn>
            <v-btn text to="/about" class="no-active">
              <span class="nav-text secondary--text py-2">About</span>
            </v-btn>
            <v-btn text to="/blog" class="no-active">
              <span class="nav-text secondary--text py-2">Blog</span>
            </v-btn>
            <v-btn text to="/contact" class="no-active">
              <span class="nav-text secondary--text py-2">Contact</span>
            </v-btn>
          </v-toolbar-items>
          <v-btn icon class="snipcart-checkout no-active">
            <v-icon color="highlight">fas fa-shopping-cart</v-icon>
          </v-btn>
        </v-row>
      </v-container>
    </v-app-bar>

    <!-- Sizes your content based upon application components -->
    <v-content>
      <!-- Provides the application the proper gutter -->
      <v-container fluid>
        <!-- If using vue-router -->
        <slot></slot>
      </v-container>
    </v-content>

    <v-footer app absolute color="#1C1C1C" class="page-footer">
      <v-row class="justify-space-around">
        <v-col cols="auto" class="text-center">
          <p class="white--text body-2">
            Created by
            <a href="https://www.codehunter.io" target="_blank">
              <span class="b-align">code</span>
              <span class="white--text font-weight-bold">Hunter</span>
            </a>
            Web Development
          </p>
        </v-col>
        <v-col cols="auto">
          <p class="white--text body-2">
            © 2020 {{ $static.metadata.siteName }} | All Rights Reserved
          </p>
        </v-col>
      </v-row>
    </v-footer>
  </v-app>
</template>

<static-query>
query {
  metadata {
    siteName
  }
}
</static-query>

<script>
export default {
  name: 'app',
  data() {
    return {
      dialog: false,
      clipped: false,
      drawer: true,
      fixed: false,
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: 'Vuetify.js',
    };
  },
};
</script>

<style lang="scss" scoped>
.navbar-icons {
  padding-top: 13px;
}
.nav-font-size {
  font-size: 1.5em;
}
.nav-text {
  font-size: 1.6em;
  font-family: 'Montserrat', sans-serif !important;
  text-transform: capitalize;
  margin: 0 10px;
}
// NAVBAR - raising fontawesome5 icons
.fa,
.fab,
.fal,
.far,
.fas {
  @media only screen and (max-width: 958px) {
    vertical-align: text-top;
  }
}
/* STYLE NAVIGATION DRAWER */
.v-list {
  padding: 50px 0 0 !important;
}
// FOOTER - bottom aligns text in codeHunter
.b-align {
  vertical-align: bottom;
  line-height: 17px;
  color: #22aa00;
  font-size: 0.85em;
  margin-right: 0.5px;
}
.page-footer {
  /* border-top: 1px solid #2a2968; */
  p {
    margin: 0px auto;
  }
}
</style>

<style lang="scss">
@import url('https://cdnjs.cloudflare.com/ajax/libs/github-markdown-css/3.0.1/github-markdown.min.css');
.markdown-body {
  box-sizing: border-box;
  min-width: 200px;
  max-width: 1000px;
  margin: 0 auto;
}
a {
  text-decoration: none !important;
  color: #1c1c1c !important;
}
.subtitle-1 {
  font-size: 1.3em !important;
}
.mont {
  font-family: 'Montserrat', sans-serif;
}

/* stops route highlighting of nav buttons */
.v-btn--active.no-active::before {
  opacity: 0 !important;
}
.v-btn:hover {
  .nav-text {
    color: #4a9df8 !important;
  }
}
.custom-header {
  font-size: 4vw !important;
}
@media screen and (max-width: 959px) {
  .custom-header {
    font-size: 2.5em !important;
  }
}
</style>
