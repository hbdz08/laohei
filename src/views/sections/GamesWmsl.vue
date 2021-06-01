<template>
  <v-theme-provider dark>
    <section
      id="GamesWmsl"
      space="56"
    >
      <v-img
        :src="require('@/assets/wmhl/bj_05.jpg')"
        min-height="minHeight"
      >
        <v-container style="margin-top:150px">
          <v-row style="width:1600px ;margin:auto">
            <v-col
              v-for="n in 12"
              :key="n"
              cols="13"
              :align-self="align"
            >
              <v-img
                lazy
                :src="require(`@/assets/wmhl/${n}.gif`)"
              />
            </v-col>
          </v-row>
        </v-container>
      </v-img>
      <v-img
        :src="require('@/assets/wmhl/bj_06.jpg')"
        min-height="minHeight"
      >
        <v-container style="margin-top:150px">
          <v-row style="width:1600px ;margin:auto">
            <v-col
              cols="13"
            >
              <v-img
                :src="require(`@/assets/wmhl/gz.gif`)"
              />
            </v-col>
          </v-row>
        </v-container>
      </v-img>
    </section>
  </v-theme-provider>
</template>

<script>
  export default {
    name: 'SectionGamesWmsl',

    provide: {
      theme: { isDark: true },
    },
    computed: {
      minHeight () {
        const height = this.$vuetify.breakpoint.mdAndUp ? '100vh' : '50vh'

        return `calc(${height} - ${this.$vuetify.application.top}px)`
      },
    },
  }

</script>
