<template>
  <div class="about">
    <h1>This is an about page</h1>
    <button @click="aaa">+1</button>
    <h1>{{ getCount }}</h1>
  </div>
</template>

<script>
// import { mapState } from 'vuex'

export default {
  name: "App",
  data(){
    return {
      localCount:'aaa'
    }
  },
  methods: {
    aaa() {
      this.$store.commit("increment");
      console.log(this.$store.state.count);
    },
  },
  computed: {
    getCount() {
      return this.$store.getters.getCount
    }
  },
};
</script>

<style lang="scss" scoped>

</style>
