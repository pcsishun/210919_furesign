<template>
  <div class="TopNav">
    <div class="logo">
      <img src="../assets/furesign.png" alt="FuResign" />
      <h1>Furesign</h1>
    </div>

    <div class="routerIcon" @click="showNav = !showNav">
      <i class="fas fa-bars"></i>
    </div>

    <div class="router">
      <router-link to="/">HOME</router-link>
      <router-link to="/marketplace">MARKETPLACE</router-link>
    </div>
  </div>

  <hr style="margin-bottom: 2px" />
  <hr style="margin-top: 2px" />

  <NavigationList class="navList" />

  <div class="contentApp" :class="{ open: showNav }">
    <router-view />
  </div>
</template>

<script>
import NavigationList from "@/components/NavigationList.vue";

export default {
  name: "TopNav",
  components: {
    NavigationList,
  },
  data: () => {
    return {
      showNav: false,
    };
  },
};
</script>

<style scoped>
@media screen and (min-width: 900px) {
  i {
    display: none !important;
  }
}

@media screen and (max-width: 900px) {
  .router {
    display: none !important;
  }
}

.router a {
  font-family: "Prompt", sans-serif;
  font-weight: 700;
  font-size: max(1.7vw, 18px);
  margin-left: 15px;
  margin-right: 15px;
  color: #e3d1c9;
}

.router a:hover {
  color: #a26854;
}

.router a.router-link-exact-active {
  color: #a26854;
}

.navList {
  position: relative;
  top: min(1vw, 15px);
}

.contentApp {
  transition: 1s transform cubic-bezier(0.19, 0.78, 0.23, 0.96);
  transform: translateY(max(-11vw, -65px));
}

.open {
  transform: translateY(10px);
}

.TopNav {
  background-color: white;
  display: flex;
  flex-wrap: nowrap;
  align-items: center;
  justify-content: space-between;
  padding: 0vw 3.5vw;
  margin: 1vw 1.5vw;
  border-radius: 20px;
}

.logo {
  display: flex;
  align-items: center;
}

.routerIcon {
  cursor: pointer;
}

img {
  width: max(5vw, 35px);
}

h1 {
  color: #a26854;
  font-family: "Prompt", sans-serif;
  font-weight: 700;
  font-size: max(1.8vw, 18px);
  margin-left: 1vw;
  margin-top: 0.5vw;
  margin-bottom: 0.5vw;
}

i {
  font-size: max(2.5vw, 13px);
  color: #2c3e50;
}

@media screen and (min-width: 1200px) {
  .TopNav {
    margin: 10px 3.5vw;
  }

  img {
    width: 55px;
  }

  h1 {
    font-size: min(1.8vw, 31px);
    margin-left: 10px;
    margin-top: 10px;
    margin-bottom: 10px;
  }

  .router a {
    font-size: min(1.7vw, 30px);
  }

  i {
    font-size: 30px;
  }
}
</style>