<template>
  <div id="app">
    <Counter name="Counter 1" :initCount="5" @emitUp="getEvent"/>
    <Counter name="Counter 2" :initCount="10" @emitUp="getEvent"/>
    <p>{{ count }}</p>
    <p>{{ globalCount }}</p>
  </div>
</template>

<script>
import Counter from '../components/Counter.vue'
import { mapState } from "vuex"
export default {
  components: {
    Counter
  },
  methods: {
    getEvent(){
      this.$store.commit("globalIncrement")
    },
    shouldNotThis(){
      this.$store.state.globalCount++;
    }
  },
  computed: {
    count(){
      return this.$store.state.globalCount
    },
    ...mapState(["globalCount"])
  }
}
</script>