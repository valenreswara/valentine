<template>
  <div class="valentine-container">
    <img v-if="yesPressed" src="https://media.tenor.com/gUiu1zyxfzYAAAAi/bear-kiss-bear-kisses.gif" alt="bear-Kissing" />
    <div v-if="yesPressed" class="text">YAAAYYYYYYYYYYYYY 💗💗🫶🫶</div>
    <img v-else class="kiss" src="https://media1.tenor.com/m/al4a1pG1f8YAAAAC/jump-bear.gif" alt="bear with heart" />
    <div v-else class="text">Will you be my valentine 🌹?</div>
    <div v-if="!yesPressed" class="both-Button">
      <button class="yesButton" :style="{ fontSize: yesButtonSize + 'px', backgroundColor: 'rgb(140, 229, 89)'}" @click="handleYesClick">MAUK :3</button>
      <button class="NoButton" @click="handleNoClick">{{ getNoButtonText() }}</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      noCount: 0,
      yesPressed: false
    };
  },
  computed: {
    yesButtonSize() {
      return this.noCount * 20 + 16;
    },
    phrases() {
      return [
        "Gmw",
        "Yakin?😔",
        "Yakin banget?😢",
        "Nanti aku sedih loh😕",
        "Plis sayang🥺",
        "Jangan gitu donggg🫤",
        "Nanti aku nangis nihh😭",
        "HWEEEE NANGISS😭💔"
      ];
    }
  },
  methods: {
    handleYesClick() {
      this.yesPressed = true;
    },
    handleNoClick() {
      this.noCount++;
    },
    getNoButtonText() {
      return this.phrases[Math.min(this.noCount, this.phrases.length - 1)];
    }
  }
};
</script>

<style>
:root {
  font-family: Inter, system-ui, Avenir, Helvetica, Arial, sans-serif;
  line-height: 1.5;
  font-weight: 400;

  color-scheme: light dark;
  color: rgba(145, 34, 34, 0.87);
  background-color: #242424;

  font-synthesis: none;
  text-rendering: optimizeLegibility;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

a {
  font-weight: 500;
  color: #646cff;
  text-decoration: inherit;
}
a:hover {
  color: #535bf2;
}

body {
  margin: 0;
  display: flex;
  place-items: center;
  min-width: 320px;
  min-height: 100vh;
}

h1 {
  font-size: 3.2em;
  line-height: 1.1;
}

button {
  border-radius: 8px;
  border: 1px solid transparent;
  padding: 0.6em 1.2em;
  font-size: 1em;
  font-weight: 500;
  font-family: inherit;
  background-color: #1a1a1a;
  cursor: pointer;
  transition: border-color 0.25s;
}
button:hover {
  border-color: #646cff;
}
button:focus,
button:focus-visible {
  outline: 4px auto -webkit-focus-ring-color;
}

@media (prefers-color-scheme: light) {
  :root {
    /* color: #213547; */
    background-color: rgb(232, 101, 252);
  }
  a:hover {
    color: #747bff;
  }
  button {
    font-size: 15px;
    color:rgb(15, 0, 0) ;
    background-color: #f53679;
  }
}

#root {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;
  text-align: center;
}
.valentine-container{
  background-color: linear-gradient(120deg, #fccb90 0%, #d57eeb 100%);
}
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.react:hover {
  filter: drop-shadow(0 0 2em #61dafbaa);
}

@keyframes logo-spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

@media (prefers-reduced-motion: no-preference) {
  a:nth-of-type(2) .logo {
    animation: logo-spin infinite 20s linear;
  }
}

.card {
  padding: 2em;
}
.kiss{
  height: 80%;
  width: 80%;
  border-radius: 60%;
}
.both-Button{
  margin: 10px;
  gap:10px
}
.read-the-docs {
  color: #888;
}
.text{
  font-family:Cambria, Cochin, Georgia, Times, 'Times New Roman', serif;
  font-size: 30px;
  color: yellowgreen;
  font-weight: 500;
  margin: 10px;
}
</style>