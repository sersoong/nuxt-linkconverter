<template>
  <v-app>
     <v-toolbar app>
      <v-toolbar-title class="headline text-uppercase">
        <span>Link Converter</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn 
      icon
      href="https://github.com/sersoong/nuxt-linkconverter"
      target="_blank"
      >
        <v-icon>fab fa-github</v-icon>
      </v-btn>
    </v-toolbar>
    
    <v-content>
        <nuxt />
    </v-content>
    <v-footer
      app
    >
      <span>&copy; 2017</span>
    </v-footer>
  </v-app>
</template>

<script>
  export default {
   
  }
</script>
