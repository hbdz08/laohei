<template>
  <section id="hero">
    <v-img
      :min-height="minHeight"

      :src="require('@/assets/35356255.jpg')"
      class="white--text"
      gradient="to bottom, rgba(11, 28, 61, .2), rgba(0,0,0,.4)"
    >
      <v-container class="fill-height px-4 py-12">
        <v-responsive
          class="d-flex align-center mx-auto"
          height="100%"
          max-width="700"
          width="100%"
        >
          <base-subheading
            weight="regular"
            title=" 专业手游定制 开新区 开新版本 专门为您订制服务 "
          />

          <base-heading
            size="text-h2"
            title="欢迎来到老黑手游"
            weight="medium"
          />

          <!-- <base-body>
          </base-body> -->

          <div
            :class="$vuetify.breakpoint.smAndDown ? 'flex-column align-start' : 'align-center'"
            class="d-flex flex-wrap"
          >
            <base-btn href="#theme-features">
              登录器下载
            </base-btn>

            <span class="font-weight-bold ml-6 mr-4 my-4" />

            <base-btn
              target="_blank"
              href="http://wpa.qq.com/msgrd?v=3&uin=767866269&site=qq&menu=yes"
            >
              联系QQ客服
            </base-btn>
            <span class="font-weight-bold ml-6 mr-4 my-4" />
          </div>
        </v-responsive>
      </v-container>
    </v-img>
  </section>
</template>

<script>
  export default {
    name: 'SectionHero',

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
