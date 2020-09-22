<template>
  <v-app-bar app clipped-left dark color="topbar">
    <v-app-bar-nav-icon @click.stop="toggleNavigationMenu" />
    <v-toolbar-title class="mr-sm-12 title">
      <v-breadcrumbs :items="crumbs" dark large>
        <template #divider>
          <v-icon>mdi-chevron-right</v-icon>
        </template>
      </v-breadcrumbs>
    </v-toolbar-title>
    <v-spacer />
    <v-btn light @click.prevent="logout">Log Out</v-btn>
  </v-app-bar>
</template>

<script>
import { mapMutations } from 'vuex'

export default {
  name: 'TheTopbar',
  computed: {
    crumbs() {
      const pathArray = this.$route.path.split('/')
      pathArray.shift()
      const breadCrumbs = pathArray.reduce((breadcrumbArray, path, idx) => {
        breadcrumbArray.push({
          path,
          to: breadcrumbArray[idx - 1]
            ? '/' + breadcrumbArray[idx - 1].path + '/' + path
            : '/' + path,
          text:
            this.$route.matched[idx] &&
            this.$route.matched[idx].meta.breadCrumb,
          exact: true,
        })
        return breadcrumbArray
      }, [])
      return this.$vuetify.breakpoint.mobile
        ? breadCrumbs.slice(-2, -1)
        : breadCrumbs
    },
  },
  methods: {
    ...mapMutations(['toggleNavigationMenu']),
    async logout() {
      await this.$auth.logout()
    },
  },
}
</script>
