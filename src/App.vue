<template>
  <div id="app">
    <!-- <nav>
      <router-link to="/">Home</router-link> |
      <router-link to="/about">About</router-link>
    </nav> -->
    <NavBarComponent />
    <router-view />
  </div>
</template>

<script>
import NavBarComponent from "./components/NavBarComponent.vue";
export default {
  components: { NavBarComponent },
  data() {
    return {
      data: {
        mealType: "breakfast",
        recipeName: "",
      },
    };
  },
  computed: {
    setRecipes() {
      return this.$store.state.setRecipes;
    },
  },
  created() {
    this.$store.dispatch("fetchRecipes", this.data);
  },
};
</script>

<style></style>
<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
