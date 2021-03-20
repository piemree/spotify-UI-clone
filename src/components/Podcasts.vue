<template >
  <div class="podcast">
    <div class="header">
      <div class="podcast-header">
        <div class="infos">
          <h2><a href="#">{{list.listHeader}}</a></h2>
          <p>{{list.listDescription}}</p>
        </div>
        <span class="see-all"><a href="#">SEE ALL</a></span>
      </div>
    </div>

    <div class="context">
      <div v-for="(item,i) in list.albums" :key="i" class="context-item">
        <div class="item">
          <div class="image-content">
            <div
              class="image"
              :style="{
                backgroundImage:
                  `url(${item.image})`,
              }"
            ></div>
            <div class="play-button">
              <svg
                height="16"
                role="img"
                width="16"
                viewBox="0 0 24 24"
                aria-hidden="true"
              >
                <polygon
                  points="21.57 12 5.98 3 5.98 21 21.57 12"
                  fill="currentColor"
                ></polygon>
              </svg>
            </div>
          </div>
          <div class="subtitle">
            <h2>{{item.title}}</h2>
            <p>{{item.description}}</p>
          </div>
        </div>
      </div>
   
    </div>
  </div>
</template>
<script>
export default {
 props:['list'],
};
</script>
<style scoped>
.context-item:hover .play-button {
  -webkit-transform: translateY(-4px);
  transform: translateY(-4px);
  opacity: 1;
}
.play-button:hover {
  animation-name: changeSize;
}
.play-button {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  position: absolute;
  right: 5px;
  bottom: 8px;
  -webkit-transform: translateY(8px);
  transform: translateY(8px);
  opacity: 0;
  -webkit-transition: all 0.3s ease;
  transition: all 0.3s ease;
  -webkit-box-shadow: 0 8px 8px rgb(0 0 0 / 30%);
  box-shadow: 0 8px 8px rgb(0 0 0 / 30%);
  z-index: 10;
  color: #fff;
  background-color: #1db954;
  display: flex;
  justify-content: center;
  align-items: center;
}

.subtitle > p {
  color: rgb(179, 179, 179);
  margin-top: 4px;
  font-size: 14px;
  font-weight: 400;
  line-height: 16px;
  letter-spacing: normal;
  text-transform: none;
}
.subtitle > h2 {
  font-size: 16px;
  font-weight: 700;
  line-height: 24px;
  letter-spacing: normal;
  text-transform: none;
  color: #fff;
}
.subtitle {
  min-height: 62px;
  display: flex;
  flex-direction: column;
  justify-content: center;
}
.image {
  /* background-image: url("https://dailymix-images.scdn.co/v2/img/3dd20002b0725be3def7a4f094493862b5045ed2/1/en/default"); */
  box-shadow: 0 8px 24px rgb(0 0 0 / 50%);
  padding-bottom: 100%;
  position: relative;
  border-radius: 12px;
  background-color: #333;
  background-size: cover;
}
.image-content {
  position: relative;
  margin-bottom: 1rem;
}
.item {
  width: 148px;
}
.context-item:hover {
  background-color: #272727;
}
.context-item {
  padding: 1rem;
  background-color: #181818;
  height: 258px;
  border-radius: 4px;
  overflow-y: hidden;
  grid-auto-rows: 0;
  grid-template-rows: 1fr;
  display: grid;
  grid-gap: 24px;
  grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
  transition: background-color 0.3s ease;
  transition-property: background-color;
  transition-duration: 0.3s;
  transition-timing-function: ease;
  transition-delay: 0s;
}
.context {
  overflow-y: hidden;
  grid-auto-rows: 0;
  grid-template-rows: 1fr;
  display: grid;
  grid-gap: 24px;
  grid-template-columns: repeat(auto-fill, minmax(180px, 1fr));
}
.see-all > a {
  color: rgb(179, 179, 179);
  font-size: 12px;
  font-weight: 800;
  line-height: 16px;
  letter-spacing: 0.1em;
  text-transform: uppercase;
}
.see-all > a:hover {
  text-decoration: underline;
}
.infos > h2 > a {
  color: white;
}
.infos > h2 > a:hover {
  text-decoration: underline;
}
.infos > h2 {
  font-size: 24px;
  font-weight: 700;
  line-height: 28px;
  letter-spacing: -0.04em;
  text-transform: none;
}
.infos > p {
  color: rgb(179, 179, 179);
  font-size: 14px;
  font-weight: 400;
  line-height: 16px;
  letter-spacing: normal;
  text-transform: none;
}
.podcast-header {
  display: flex;
  margin-bottom: 1rem;
  align-items: flex-end;
  justify-content: space-between;
}
.header {
  width: 100%;
  height: 65px;
}
.podcast {
  width: 100%;
  height: 368px;
}
</style>