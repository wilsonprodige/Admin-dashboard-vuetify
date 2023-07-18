
<template>
  <v-app id="inspire">
    <v-navigation-drawer v-model="drawer" app>
    <SideBar/> 
    </v-navigation-drawer>   
    <v-main>
      <v-app-bar app
        color="white">
        
        <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
        <v-app-bar-title>AICS-Attend</v-app-bar-title>
        <v-col lg="5" cols="12">
          <v-form class="mt-5">
            <v-text-field 
            append-inner-icon="mdi-magnify"
            density="solo"
            :loading="loading"
            outlined
            placeholder="Search here"/>
          </v-form>

        </v-col>

        <v-menu>
        <template v-slot:activator="{props}">
          <v-span v-bind="props" style="cursor: pointer" class="mx-5 mr-10">
            <v-chip link>
              <v-badge dot bottom offset-y="10" offsetX="10" color="#5E9FFF">
                <v-avatar size="40">
                  <v-img src="./assets/profile5.jpg"/>
                </v-avatar>
              </v-badge>
              <span>Sharli Chin</span>
            </v-chip>
          </v-span>
        </template>
        <v-list width="250" class="py-0">
              <v-list-item>
                <v-btn prepend-icon="mdi-account-cog">Account</v-btn>
              </v-list-item>
              <v-list-item>
                <v-btn prepend-icon="mdi-logout">Logout</v-btn>
              </v-list-item>
          </v-list>
        </v-menu>





      </v-app-bar>
      <v-container
        class="py-8 px-6"
        fluid
      >
        <v-row>
          <v-col
            v-for="card in cards"
            :key="card"
            cols="12"
          >
            <v-card>

              <v-list lines="two">
                <v-list-subheader>{{ card }}</v-list-subheader>
                <template v-for="n in 6" :key="n">
                  <v-list-item>
                    <template v-slot:prepend>
                      <v-avatar color="grey-darken-1"></v-avatar>
                    </template>

                    <v-list-item-title>Message {{ n }}</v-list-item-title>

                    <v-list-item-subtitle>
                      Lorem ipsum dolor sit amet, consectetur adipisicing elit. Nihil repellendus distinctio similique
                    </v-list-item-subtitle>
                  </v-list-item>

                  <v-divider
                    v-if="n !== 6"
                    :key="`divider-${n}`"
                    inset
                  ></v-divider>
                </template>
              </v-list>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-main>
  </v-app>
</template>

<script>
  // eslint-disable-next-line
  import SideBar from './components/SideBar.vue';
  // eslint-disable-next-line
  //import Header from './components/Header.vue';

  export default {
  components: {SideBar},
    data: () => ({
      cards: ['Today', 'Yesterday'],
      drawer: null,
      
    }),
  }
</script>
  <router-view/>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
