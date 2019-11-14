<template>
  <v-app>
    <v-app-bar
      app
      color="primary"
      dark
    >
      <v-row>
        <v-col cols="2">
          <v-btn text @click="pushToRoute('home')">Usuario</v-btn>
        </v-col>
        <v-col cols="2">
          <v-btn text @click="pushToRoute('about')"> Curso</v-btn>
        </v-col>
      </v-row>
    </v-app-bar>
    <v-content>
      <router-view/>
    </v-content>
  </v-app>
</template>

<script>
export default {
  name: 'App',
  data: () => ({
    //
  }),
  methods: {
    pushToRoute(value) {
      this.$router.push({ name: value });
    },
  },
};
</script>
