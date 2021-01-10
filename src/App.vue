<template>
  <v-app>
    <v-main
      style="
      background: rgb(200,8,95);
      background: linear-gradient(90deg, rgba(200,8,95,1) 50%, rgba(221,10,125,1) 50%);
      "
    >
      <HelloWorld/>
    </v-main>
  </v-app>
</template>

<script>
import HelloWorld from './components/HelloWorld';

export default {
  name: 'App',

  components: {
    HelloWorld,
  },
};
</script>
