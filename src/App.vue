<template>
  <v-app>
    <advices/>
  </v-app>
</template>

<script>
import advices from './components/advices';

export default {
  name: 'App',

  components: {
    advices,
  },

  data: () => ({
    //
  }),
};
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Manrope:wght@800&display=swap');
#app{
  background-color: hsl(218, 23%, 16%);
  font-family: 'Manrope', sans-serif;

}
</style>
