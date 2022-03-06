<template>
  <div>
    <nav>
      <ul>
        <router-link to="/">Home</router-link>
        <router-link to="/about">About</router-link>
        <router-link to="/contact">Contact</router-link>
      </ul>
    </nav>
    <button @click="Home">Home</button>
    <button @click="About">About</button>
    <button @click="Contact">Contact</button>
    <div>
      <ul>
        <li v-for="(userId, index) in userIds" :key="index">
          <router-link :to="{ name: 'Profile', params: { user_id: userId } }"
            >Profile {{ userId }}</router-link
          >
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "Navbar",
  data() {
    return {
      userIds: ["1", "2", "3", "4", "5", "6", "7", "8"],
    };
  },
  methods: {
    Home() {
      this.$router.push({ name: "Home" });
    },
    About() {
      this.$router.push({ name: "About" });
    },
    Contact() {
      this.$router.push({ name: "Contact" });
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
nav {
  text-align: center;
}

nav ul {
  padding: 0;
}

nav a {
  display: inline-block;
  list-style-type: none;
  margin: 0;
  padding: 10px;
  text-decoration: none;
  font-weight: bold;
  color: burlywood;
}

a.router-link-exact-active {
  color: blueviolet;
}
</style>
