<template>
  <div id="app">
    <div class="wrapper">
       <HeroVideo />
       <Form @show-summary="submit()" v-if="!summary" :form="form"/>
       <Sumup
       @close-booking="close()"
       :form="form"
        v-if="summary"/>
    </div>
  </div>
</template>

<script>
import HeroVideo from './components/HeroVideo.vue';
import Form from './components/Form.vue';
import Sumup from './components/Sumup.vue';



export default {
  name: 'app',
  components: {
    HeroVideo,
    Form,
    Sumup,
  },
  data() {
    return {
      summary: false,
      form: {
        city: '',
        from: '',
        to: '',
        selected: '',
        options: [
        {text: '1 Guest', value: '1'},
        {text: '2 Guest', value: '2'},
        {text: '3 Guest', value: '3'},
        {text: '4 Guest', value: '4'},
        {text: '5 Guest', value: '5'},
        {text: '6 Guest', value: '6'},
      ],
    }
  }
  },

  methods: {
    submit() {
      this.summary = true;
    },

    close() {
      this.summary = false;
      this.form.city = '';
      this.form.from = '';
      this.form.to = '';
      this.form.selected = '';

    }
  }
};
</script>

<style lang="scss">
html {
  box-sizing: border-box;
}
*, *:before, *:after {
  box-sizing: inherit;
  padding: 0;
  margin: 0;
}

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

.wrapper {
  height: 100vh;
}
</style>
