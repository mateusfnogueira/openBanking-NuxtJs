<template>
  <div class="header">
    <v-navigation-drawer
      v-model="drawer"
      :mini-variant="miniVariant"
      clipped="true"
      fixed
      app
    >
      <v-list>
        <v-list-item
          v-for="(item, i) in items"
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
    <v-app-bar :clipped-left="clipped" fixed app>
      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />
      <v-btn icon @click.stop="miniVariant = !miniVariant">
        <v-icon>mdi-{{ `chevron-${miniVariant ? "right" : "left"}` }}</v-icon>
      </v-btn>
      <v-toolbar-title v-text="title" />
      <v-spacer />
    </v-app-bar>
    <v-main>
      <v-container>
        <nuxt />
      </v-container>
    </v-main>
  </div>
</template>

<script>
export default {
  data() {
    return {
      clipped: true,
      drawer: true,
      items: [
        {
          icon: "mdi-apps",
          title: "DashBoard",
          to: "/"
        },
        {
          icon: "mdi-bank-transfer",
          title: "Transitions",
          to: "/Transitions"
        },
        {
          icon: "mdi-account-circle",
          title: "User",
          to: "/UserEdit"
        },
        {
          icon: "mdi-logout",
          title: "Logout",
          to: "/Login"
        }
      ],
      miniVariant: true,
      right: true,
      rightDrawer: false,
      title: "XBank"
    };
  }
};
</script>

<style></style>
