<template>
  <div>
    <h1 id="header">{{ header }}</h1>
    <h2>{{ headerUppercase }}</h2>

    <div v-if="apiError">
    
    
    
    
    </div>

    <div v-for="(item, index) in list" :key="index">
      Hola: {{ format(item) }}.

      <div v-if="index > 0">Soy un índice mayor que cero!!</div>
    </div>

    <ErrorButton @click="fullHeaderChange"/>

    <ErrorButton @click="apiError = !apiError" />
  </div>
</template>

<script>

import ErrorButton from './components/ErrorButton.vue'

export default {
  name: "App",
  props: [],
  components: { ErrorButton },
  data() {
    return {
      header: "Empower Your Business With Stunning Design!",
      apiError: false,
      list: ["one", "two", "three"],
    };
  },
  computed: {
    headerUppercase() {
      return this.header.toUpperCase();
    },
  },
  methods: {
    fullHeaderChange() {
      this.changeHeaderColor();
      this.changeHeaderName();
    },
    changeHeaderColor() {},
    changeHeaderName() {
      this.header = "A otro nombre";
    },
    format(item) {
      return item.toUpperCase();
    },
  },
  mounted() {},
};
</script>

<style scoped>
#header {
  color: purple;
}

div {
  padding: 30px;
}
</style>
