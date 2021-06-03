<template>
  <div id="app">
    <Counter name="Counter 1" :initCount="5" @emitUp="getEvent"/>
    <Counter name="Counter 2" :initCount="10" @emitUp="getEvent"/>
    <p>{{ primitiveStore.$data.globalCount }}</p>
    <input type="text" v-model="primitiveStore.$data.globalCount">
  </div>
</template>

<script>
import Counter from '../components/Counter.vue'
import primitiveStore from '../primitiveStore.js'
export default {
  components: {
    Counter
  },
  data(){
    return {
      primitiveStore
    }
  },
  methods: {
    getEvent(payload){
      this.primitiveStore.$data.globalCount++;
    }
  }
}
</script>