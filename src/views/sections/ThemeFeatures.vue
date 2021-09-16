<template>
  <base-section id="theme-features">
    <base-section-heading
      title="[老黑版本介绍] 《倾情推荐所有版本》"
      style="color:red"
    >
      老黑精品手游，经典耐玩，为回馈广大玩家，每周推出一个免费顶赞沙娟的端游版本以供娱乐

      <v-btn
        color="red"
        class="ma-4 white--text"
        href="https://hbdz08.cn/img/20210520232356.jpg"
        target="_blank"
      >
        点我关注微信公众号（获取沙捐码）
        <v-icon
          right
          dark
        >
          mdi-account-tie-voice
        </v-icon>
      </v-btn>
    </base-section-heading>

    <v-container>
      <v-simple-table
        class="simple-table"
      >
        <thead>
          <tr>
            <th class="text-left">
              推荐服务器
            </th>
            <th class="text-left">
              版本介绍(开区时间)
            </th>
            <th class="text-left">
              开区状态
            </th>
            <th class="text-left">
              下载网站
            </th>
          </tr>
        </thead>
        <tbody>
          <tr
            v-for="item in data.list"
            :key="item.name"
          >
            <td
              style="color:#72147e"
              v-html="item.name"
            >
              {{ item.name }}
            </td>
            <td
              style="color:#ff5200;"
            >
              <div
                v-if="item.openTime != ''"
                v-html="item.openTime "
              />
              <div
                v-if="item.version != ''"
                v-html="item.version "
              />
            </td>
            <td
              class="state-color"
              style="color:#f21170;"
            >
              {{ item.stateName }}
            </td>
            <td>
              <v-btn
                color="#fa9905"
                class="ma-2 white--text"
                :href="item.downloadLink"
                target="_blank"
              >
                下载
                <v-icon
                  right
                  dark
                >
                  mdi-cloud-download
                </v-icon>
              </v-btn>
            </td>
          </tr>
        </tbody>
      </v-simple-table>
      <div class="py-8" />
      <base-section-heading
        title="回馈长期光顾老黑旗下版本的所有老铁每个版本充值的玩家,每个充值账号充值都可以转新区"
        style="color:red"
      />

      <base-section-heading
        title="关于充值玩家转区联系客服 不支持沙捐版本，版本统一游戏内充"
        style="color:red"
      />
      <base-section-heading
        title="本站尊重知识产权，如果我们无意侵犯了您的权益，请告知我们"
        style="color:red"
      />
    </v-container>
  </base-section>
</template>
<style lang="scss" scoped>
.theme--light.v-data-table > .v-data-table__wrapper > table > thead > tr:last-child > th  {
   font-size: 20px;
}

</style>
<script>
  import { getList } from '@/api/gameVersion'

  export default {
    data () {
      return {
        data: null,
        listQuery: {
          domain: 3,
        },
      }
    },
    mounted () {
      const base = window.location.host
      console.log(base)

      if (base === 'kslaohei.com' || base === 'www.laoheisf.com:8088') {
        this.listQuery.domain = 1
      }
      getList(this.listQuery).then(respone => {
        this.data = respone.data.data
      })
    },

  }
</script>
