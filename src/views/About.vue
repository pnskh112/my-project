<template>
  <div class="about">
    <h1>This is an about page</h1>
    <p>{{ profile }}</p>
  </div>
</template>
<script>
import { mapState } from "vuex"
export default {
  computed: {
    ...mapState(["profile"])
  },
  mounted(){
    this.$store.dispatch("fetchGithubProfile",{user_id: "pnskh112"})
  },
}
</script>

