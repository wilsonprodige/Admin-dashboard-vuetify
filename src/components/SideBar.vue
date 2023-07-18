<template>
      <v-sheet
        color="#5E9FFF"
        class="pa-4"
      >
        <v-avatar
          class="mb-4"
          color="white"
          size="64">
          <v-img aspect-ratio="50" src="../assets/profile4.jpg"></v-img>
        </v-avatar>

        <h4 class="white-text">john@google.com</h4>
      </v-sheet>

      <v-divider></v-divider>

      <v-list>
        <v-list-item
          v-for="[icon, text] in links"
          :key="icon"
          link
        >
          <template v-slot:prepend>
            <v-icon>{{ icon }}</v-icon>
          </template>

          <v-list-item-title>{{ text }}</v-list-item-title>
        </v-list-item>
      </v-list>
   
    
</template>

<script>
export default {
    name:'SideBar',
    props:['drawer'],
    data(){
        return{
            links: [
        ['mdi-view-dashboard', 'Dashboard'],
        ['mdi-account', 'Profile'],
        ['mdi-apps-box', 'Product'],
        ['mdi-order-bool-descending-variant', 'Order'],
        ['mdi-cog', 'System Settings']
      ]
        }
    }


}
</script>

<style>

</style>