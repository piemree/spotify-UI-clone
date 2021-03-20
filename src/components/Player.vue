<template >
  <div @mouseup="opaZero" class="player">
    <div class="playing-bar-left"></div>
    <section class="main-controllers">
      <div class="controll-buttons">
        <button class="btn btn-howered"><i class="fas fa-random"></i></button>
        <button class="btn btn-howered">
          <i class="fas fa-step-backward"></i>
        </button>
        <button
          @mousedown="playEffect = 'scaled'"
          @mouseup="playEffect = ''"
          :class="`btn btn-play ${playEffect}`"
        >
          <i class="fas fa-play"></i>
        </button>
        <button class="btn btn-howered">
          <i class="fas fa-step-forward"></i>
        </button>
        <button class="btn btn-howered"><i class="fas fa-redo"></i></button>
      </div>

      <div class="playback-bar">
        <div class="progress-time">0:00</div>
        <div class="bar-capsule">
          <button class="btn-dragger"></button>
          <div class="progress">
            <div class="progress-bar">
              <div style="transform: translateX(-100%)" class="moved-bar"></div>
            </div>
          </div>
        </div>
        <div class="progress-time">0:00</div>
      </div>
    </section>
    <div class="playing-bar-right">
      <button class="btn btn-howered"><i class="fas fa-list"></i></button>
      <button class="btn btn-howered"><i class="fas fa-desktop"></i></button>
      <div class="sound">
        <button
          @mousemove="btnOpacity = 1"
          @mouseout="btnOpacity = 0"
          @click="offset = 50"
          class="btn btn-howered"
        >
          <i v-if="offset > 0" class="fas fa-volume-up"></i>
          <i v-else class="fas fa-volume-mute"></i>
        </button>
        <div
          @mouseenter="btnOpacity = 1"
          @mouseleave="isClicked ? (btnOpacity = 1) : (btnOpacity = 0)"
          @mousedown="down($event)"
          @mousemove="move($event)"
          @click="moveClick($event)"
          class="progress-content"
        >
          <div class="bar-capsule">
            <button
              :style="{ opacity: btnOpacity, left: `${offset}%` }"
              class="btn-dragger"
            ></button>
            <div class="progress-bar">
              <div
                class="moved-bar"
                :style="{
                  transform: `translateX(${-100 + offset}%)`,
                  backgroundColor: btnOpacity == 1 ? '#1db954' : '#b3b3b3',
                }"
              ></div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      playEffect: "",
      btnOpacity: 0,
      isClicked: false,
      offset: 0,
    };
  },
  watch: {
    offset() {
      console.log("offset", this.offset);
    },
    isClicked() {
      console.log("click", this.isClicked);
    },
    btnOpacity() {
      console.log("btnOpacity", this.btnOpacity);
    },
  },
  methods: {
    opaZero() {
      //this.btnOpacity = 0;
      window.addEventListener("mouseup", () => {
        this.isClicked = false;
      });
    },
    move(e) {
      if (this.isClicked) {
        this.offset = e.offsetX;
      }
    },
    down(e) {
      this.isClicked = true;
      if (this.isClicked) {
        this.offset = e.offsetX;
      }
    },
    moveClick(e) {
      this.offset = e.offsetX;
    },
  },
};
</script>
<style scoped>
.bar-capsule:hover .btn-dragger {
  opacity: 1;
}
.btn-dragger {
  height: 12px;
  width: 12px;
  margin: 0 0 0 -6px;
  background-color: white;
  border-radius: 50%;
  border: none;
  outline: none;
  position: absolute;
  top: -100%;
  z-index: 100;
  pointer-events: none;
}
.player {
  background-color: #181818;
  border-top: 1px solid #282828;
  position: fixed;
  bottom: 0;
  width: 100%;
  min-width: 768px;
  height: 90px;
  padding: 0 1rem;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.main-controllers {
  width: 40%;
  max-width: 722px;
  min-width: 295px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.controll-buttons {
  width: 42%;
  min-width: 224px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin: 0 0 12px;
}
.bar-capsule {
  width: 100%;
  position: relative;
}
.playback-bar {
  width: 100%;
  display: flex;
  align-items: center;
}
.progress-time {
  min-width: 40px;
  height: 1rem;
  text-align: center;

  color: #b3b3b3;
  font-size: 13px;
  font-weight: 400;
}
.progress {
  width: 100%;
  background-color: inherit;
}
.progress-bar {
  height: 4px;
  width: 100%;
  background-color: #535353;
  border-radius: 4px;
  overflow: hidden;
  overflow-x: hidden;
  overflow-y: hidden;
  pointer-events: none;
}
.btn {
  display: flex;
  justify-content: center;
  align-items: center;
  border: none;
  outline: none;
  width: 32px;
  height: 32px;
}
.btn-play {
  border-radius: 50%;
  font-size: 11px;
}
.scaled {
  transform: scale(0.9);
}
.btn-howered {
  background-color: inherit;
  color: #b3b3b3;
}
.btn-howered:hover {
  color: #ffffff;
}

.playing-bar-left {
  width: 30%;
  min-width: 180px;
}
.playing-bar-right {
  width: 30%;
  min-width: 180px;
  height: 32px;
  display: flex;
  align-items: center;
  justify-content: flex-end;
}
.sound {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.progress-content {
  height: 30px;
  width: 100px;
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 101;
}
.moved-bar {
  background-color: #1db954;
  width: 100%;
  height: 100%;
  border-radius: inherit;
  pointer-events: none;
  position: relative;
}
</style>