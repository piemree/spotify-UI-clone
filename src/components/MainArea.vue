<template >
  <div class="main">
    <header>
      <div class="allheader">
        <div class="back-next-btn">
          <button class="before-btn">
            <svg
              role="img"
              focusable="false"
              height="24"
              width="24"
              viewBox="0 0 24 24"
              class="Svg-sc-1usfroi-0 jUuLJy _6fe5d5efc9b4a07d5c424071ac7cdacb-scss"
            >
              <polyline
                points="16 4 7 12 16 20"
                fill="none"
                stroke="#181818"
              ></polyline>
            </svg>
          </button>
          <button class="after-btn">
            <svg
              role="img"
              focusable="false"
              height="24"
              width="24"
              viewBox="0 0 24 24"
              class="Svg-sc-1usfroi-0 jUuLJy _6fe5d5efc9b4a07d5c424071ac7cdacb-scss"
            >
              <polyline
                points="8 4 17 12 8 20"
                fill="none"
                stroke="#181818"
              ></polyline>
            </svg>
          </button>
        </div>
        <div class="user-section">
          <button class="signup">SIGN UP</button>
          <button class="login">LOG IN</button>
        </div>
      </div>
    </header>
    <main>
      <Podcasts :list="Ceza" />
      <Podcasts :list="Trap" />
      <Podcasts :list="yourListening" />
    </main>
  </div>
</template>
<script>
import Podcasts from "./Podcasts";
export default {
  data() {
    return {
      Ceza: {
        listHeader: "Best of Ceza",
        listDescription: "",
        albums: [
          {
            image:
              "https://i.scdn.co/image/ab67616d0000b2732a07bf1912730d354453a4ca",
            title: "Rapstar",
            description: "Ceza",
          },
          {
            image:
              "https://i.scdn.co/image/ab67616d0000b27309dd7da0003a4a677e21f2c5",
            title: "Suspus",
            description: "Ceza",
          },
          {
            image:
              "https://i.scdn.co/image/ab67616d0000b2734a7f13cd6d9d7d1ab9bfda35",
            title: "Yerli Plaka",
            description: "Ceza",
          },
          {
            image:
              "https://i.scdn.co/image/f9ce6868cab624cd14488a884f00100ddab05457",
            title: "Medcezir",
            description: "Ceza",
          },
          {
            image:
              "https://i.scdn.co/image/ab67706f000000026ed9a95df5279b1c9283f99a",
            title: "This is Ceza",
            description: " türkçe rap denince akla gelen ilk isim",
          },
        ],
      },
      Trap: {
        listHeader: "More like Khontkar",
        listDescription: "",
        albums: [
          {
            image:
              "https://i.scdn.co/image/ab67616d0000b27380f15a56e817c4724a850dfc",
            title: "İşin Mutfağı",
            description: "Artz",
          },
          {
            image:
              "https://i.scdn.co/image/ab67616d0000b273b2213a5e6ef973b08163d97c",
            title: "Yak Yak",
            description: "Şeyn",
          },
          {
            image:
              "https://i.scdn.co/image/ab67616d0000b273f1081c95ea5800b9b34850b9",
            title: "Trapanasyon",
            description: "Ceg",
          },
          {
            image:
              "https://i.scdn.co/image/ab67616d0000b273741f4bcc72ba52af1615aa02",
            title: "110",
            description: "İstanbul Trip",
          },
          {
            image:
              "https://i.scdn.co/image/ab67706f000000027da6d43f86eb52acd4b9deca",
            title: "Harekete Geç",
            description: "Egzersizin her anına tempo tutacak şarkılar.",
          },
        ],
      },
      yourListening: {
        listHeader: "Braced on your recent listening",
        listDescription: "Inspired by your recent activity",
        albums: [
          {
            image:
              "https://i.scdn.co/image/ab67706f0000000278b6084e35bc2f928fb7c6ee",
            title: "Yılın Şarkıları 2020",
            description: "Türkiye'nin bu sene en çok dinlediği şarkılar",
          },
          {
            image:
              "https://i.scdn.co/image/ab67706f00000002b62d29eb9739a628c285112d",
            title: "Top Tracks of 2019",
            description: "Most streamed songs globally on Spotify",
          },
          {
            image:
              "https://i.scdn.co/image/ab67706f000000022beb4afd7fe086b75229de46",
            title: "Top Male Artists of 2019",
            description: "Most streamed Males",
          },
          {
            image:
              "https://i.scdn.co/image/ab67706f000000023edd7170d0fa40df191995db",
            title: "Duş ŞArkıları",
            description: "Güne şarkı söyleyerek ve tertemiz başla!",
          },
          {
            image: "https://misc.scdn.co/liked-songs/liked-songs-300.png",
            title: "Liked Songs",
            description: "",
          },
        ],
      },
    };
  },
  components: {
    Podcasts,
  },
};
</script>
<style scoped>
.login{
    background-color: #fff;
  color: #000;
}
.signup {
  background-color: inherit;
  color: #fff;
}
.user-section button:hover{
    transform: scale(1.04);
}
.user-section button{
    outline: none;
    border: none;
    height: 100%;
    width: 100%;
    border-radius:50px;
        font-size: 12px;
    line-height: 18px;
    font-weight: 700;
    letter-spacing: 1.76px;
    text-transform: uppercase;
    cursor: pointer;
}
.user-section {
  background-color: inherit;
  padding-right: 2rem;
  width: 288px;
  height: 38px;
  display: flex;
  align-items: center;
  justify-content: space-around;
}
polyline {
  stroke: white;
}
.back-next-btn button {
  background-color: rgba(0, 0, 0, 0.7);
  color: #fff;
  border: none;
  outline: none;
  height: 32px;
  width: 32px;
  border-radius: 50%;
  margin-right: 1rem;
  opacity: 0.6;
  cursor: not-allowed;
}
.main {
  width: 100%;
  height: fit-content;
  background-color: #121212;
  overflow: scroll;
  min-width: 1066px;
}

.allheader {
  width: 1066px;
  height: 100%;
  padding-right: 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

header {
  background-color: #070707;
  width: 100%;
  height: 60px;
  position: fixed;
  z-index: 102;
  padding: 1rem 2rem;
}
main {
  display: grid;
  grid-gap: 32px;
  padding-top: 24px;
  padding: 1.5rem 2rem 0;
}
</style>