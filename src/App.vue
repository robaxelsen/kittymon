<template>
  <v-app>
    <v-toolbar color="blue" app>
      <v-toolbar-title class="headline text-uppercase">
        <span>KITTYMON</span>
      </v-toolbar-title>
      <v-spacer></v-spacer>
      <v-btn
        flat
      >
        <span class="mr-2">Gotta claw 'em all!</span>
      </v-btn>
    </v-toolbar>

    <v-content>
      <KittyCards />
    </v-content>
  </v-app>
</template>

<script>
import KittyCards from './components/KittyCards'
export default {
  name: 'App',
  components: {
    KittyCards
  }
}
</script>
