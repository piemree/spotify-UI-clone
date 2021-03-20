<template>
  <div id="app" class="Root">
    <nav><SideBar /></nav>
    <main><MainArea /></main>
    <footer><Player /></footer>
  </div>
</template>

<script>
import Player from "./components/Player";
import SideBar from "./components/SideBar";
import MainArea from "./components/MainArea";
export default {
  name: "App",
  components: {
    Player,
    SideBar,
    MainArea,
  },
};
</script>

<style>
* {
  -webkit-font-smoothing: antialiased;
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  list-style: none;
  text-decoration: none;
  font-family: spotify-circular, spotify-circular-cyrillic,
    spotify-circular-arabic, spotify-circular-hebrew, Helvetica Neue, helvetica,
    arial, Hiragino Kaku Gothic Pro, Meiryo, MS Gothic, sans-serif;
}

#app {
  min-width: 100%;
  min-height: 100vh;
}
#app {
  display: grid;
  width: 100%;
  height: 100vh;
  grid-template-areas:
    "nav main main"
    "foot  foot foot";
  grid-template-rows: 1fr 90px;
  grid-template-columns: 300px 1fr;
}

#app > nav {
  grid-area: nav;
}

#app > main {
  grid-area: main;
}

#app > footer {
  grid-area: foot;
  z-index: 101;
}

::-webkit-scrollbar {
  all: unset;
  width: 0;
}



</style>
