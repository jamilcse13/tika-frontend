<template>
  <div>
    <h1 v-if="apiValue">Check: {{ apiValue }}</h1>
    <button @click.prevent="testBackendRequest">Request Api</button>
    <Tutorial/>
  </div>
</template>

<script>
export default {
  data() {
    return {
      apiValue: ''
    }
  },

  mounted() {

  },

  methods: {
    testBackendRequest() {
      this.$axios.get('/test').then(res => {
        this.apiValue = res.data;
      })
    }
  }
}
</script>
