<template>
<div>
        <v-app-bar color="#558B2F" dark>
          <v-app-bar-nav-icon @click="drawer = true"></v-app-bar-nav-icon>
          <v-toolbar-title>Campeonato Brasileiro ⚽</v-toolbar-title>
            <template v-slot:activator="{ on, attrs }">
              <v-btn
                icon
                v-bind="attrs"
                v-on="on"
              >
                <v-icon>mdi-dots-vertical</v-icon>
              </v-btn>
            </template>
        </v-app-bar>
        <v-navigation-drawer
          v-model="drawer"
          absolute
          temporary
        >
          <v-list
            nav
            dense
          >
            <v-list-item-group
              v-model="group"
              active-class="green--text text--light-lighten-1"
            >
              <router-link to="/">
                <v-list-item>
                  <v-list-item-icon>
                    <v-icon>mdi-home-outline</v-icon>
                  </v-list-item-icon>
                  <v-list-item-title>Início</v-list-item-title>
                </v-list-item>
              </router-link>
              <router-link to="/classificacao">
                <v-list-item>
                  <v-list-item-icon>
                    <v-icon>mdi-trophy-variant-outline</v-icon>
                  </v-list-item-icon>
                  <v-list-item-title>Classificação</v-list-item-title>
                </v-list-item>
              </router-link>
            </v-list-item-group>
          </v-list>
        </v-navigation-drawer>
      </div>
</template>

<script>
export default {
    name: 'AppTopBar',
    data: () => ({
      drawer: false,
      group: null,
    }),
    
}
</script>

<style scoped>
a {
  text-decoration: none;
}
</style>