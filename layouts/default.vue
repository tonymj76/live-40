<template>
  <v-app class="bg">
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      :clipped="clipped"
      fixed
      temporary
      app
      class="success"
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in navItems"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar :clipped-left="clipped" fixed app flat grey lighten-4>
      <v-app-bar-nav-icon
        class="hidden-sm-and-up"
        @click.stop="drawer = !drawer"
      />
      <v-toolbar-title router to="/" v-text="title" />
      <v-spacer />
      <div v-for="item in navItems" :key="item.title">
        <v-btn
          text
          retain-focus-on-click
          active-class="active"
          class="btn-color grey--text hidden-sm-and-down"
        >
          {{ item.title }}
        </v-btn>
      </div>
    </v-app-bar>
    <v-content>
      <v-container pa-0>
        <nuxt />
      </v-container>
    </v-content>
    <v-footer :fixed="fixed" app>
      <span>&copy; {{ new Date().getFullYear() }}</span>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      clipped: false,
      drawer: false,
      fixed: false,
      navItems: [
        {
          title: 'Exercises',
          icon: 'mdi-apps',
          to: '/'
        },
        {
          title: 'Weight Loss',
          icon: 'mdi-apps',
          to: '/'
        },
        {
          title: 'Nutrition',
          icon: 'mdi-apps',
          to: '/'
        },
        {
          title: 'Features',
          icon: 'mdi-apps',
          to: '/'
        }
      ],
      miniVariant: false,
      title: 'Living Live @ 40'
    };
  }
};
</script>

<style lang="scss" scoped>
.btn-color {
  :hover {
    color: #f01616;
  }
  :focus {
    color: #f01616 !important;
  }
}
.active {
  color: #f01616 !important;
}
</style>
