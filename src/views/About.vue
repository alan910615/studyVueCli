<template>
  <div class="about">
    <h1>This is an about page</h1>
    <button @click="aaa">+1</button>
  </div>
</template>

<script>
import { mapState } from 'vuex'

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
  computed: mapState({
    // 箭头函数可使代码更简练
    count: state => state.count,
    countPlusLocalState(state) {
      return state.count + this.localCount
    }
  })
};
</script>

<style lang="scss" scoped>
h1 {
  color: red;
}
</style>
