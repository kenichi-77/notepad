<template>
  <div class="home">
    <ul v-for="memo in newest" :key="memo.id">
      <li>
        <router-link :to="{ name: 'Edit', params: { id: memo.id } }">{{
          memo.body
        }}</router-link>
      </li>
    </ul>
    <!-- <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  </div>
</template>

<style>
textarea {
  width: 100%;
  height: 10em;
}
button {
  border: 1px solid #333;
  background-color: #333;
  color: #fff;
  padding: 10px 20px;
  margin-top: 10px;
}
</style>

<script>
// @ is an alias to /src
// import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {
    // HelloWorld,
  },
  computed: {
    newest: function() {
      return this.$store.state.memos.slice().reverse();
    },
  },
};
</script>
