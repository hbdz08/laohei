<template>
  <div>
    <v-app-bar
      id="home-app-bar"
      app
      elevation="1"
      elevate-on-scroll
      height="100"
    >
      <base-img

        :src="require(`@/assets/1620887491630.png`)"
        class="mr-3 hidden-xs-only"
        contain
        max-width="100"
        width="100%"
      />

      <!-- <base-img
        :src="require(`@/assets/zero-logo-${$vuetify.theme.isDark ? 'dark' : 'light'}.svg`)"
        contain
        max-width="96"
        width="100%"
      /> -->

      <v-spacer />

      <div>
        <v-tabs
          class="hidden-sm-and-down"
          optional
          background-color="transparent"
        >
          <v-tab
            v-for="(name, i) in items"
            :key="i"
            :to="{ name }"
            :exact="name === '棣栭〉'"
            :ripple="false"
            class="font-weight-bold"
            min-width="96"
            text
          >
            {{ name }}
          </v-tab>
        </v-tabs>
      </div>

      <v-app-bar-nav-icon
        class="hidden-md-and-up"
        @click="drawer = !drawer"
      />
    </v-app-bar>
  </div>
</template>

<script>
  export default {
    name: 'HomeAppBar',

    data: () => ({
      drawer: null,
      items: [
        // '棣栭〉',
        // '鍏呭€煎叆鍙�',
      ],
    }),
  }
</script>

<style lang="sass">
  #home-app-bar
    .v-tabs-slider
      max-width: 24px
      margin: 0 auto

    .v-tab
      &::before
        display: none
</style>
