<template>
  <body>
    <title>Cuties</title>
    <h1 class="title">
      Cuties in my life!:) Click the 'love it' button when hovering over images!
    </h1>
    <p class="Totallikes">
      The total likes you have been sent to this photos are:{{
        counter01 + counter02 + counter03 + counter04
      }}
    </p>
    <div class="image">
      <img
        id="image01"
        :src="picture1Hover"
        @mouseover="hover1 = true"
        @mouseleave="hover1 = false"
      />
      <div class="image__overlay image__overlay--primary">
        <button @click="counter01++">I love it!</button>
        <p>You have sent {{ counter01 }} likes to this photo.</p>
      </div>
    </div>

    <div class="image">
      <img
        id="image02"
        :src="picture2Hover"
        @mouseover="hover2 = true"
        @mouseleave="hover2 = false"
      />
      <div class="image__overlay image__overlay--primary">
        <button @click="counter02++">I love it!</button>
        <p>You have sent {{ counter02 }} likes to this photo.</p>
      </div>
    </div>

    <div class="image">
      <img
        id="image03"
        :src="picture3Hover"
        @mouseover="hover3 = true"
        @mouseleave="hover3 = false"
      />
      <div class="image__overlay image__overlay--primary">
        <button @click="counter03++">I love it!</button>
        <p>You have sent {{ counter03 }} likes to this photo.</p>
      </div>
    </div>

    <div class="image">
      <img
        id="image04"
        :src="picture4Hover"
        @mouseover="hover4 = true"
        @mouseleave="hover4 = false"
      />
      <div class="image__overlay image__overlay--primary">
        <button @click="counter04++">I love it!</button>
        <p>You have sent {{ counter04 }} likes to this photo.</p>
      </div>
    </div>
  </body>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      pictureStatic: require("@/assets/picture01.jpeg"),
      pictureGif01: require("@/assets/picture02.jpeg"),
      pictureGif02: require("@/assets/picture03.jpeg"),
      pictureGif03: require("@/assets/picture04.jpg"),
      pictureGif04: require("@/assets/picture05.jpg"),
      pictureGif05: require("@/assets/picture06.jpeg"),
      pictureGif06: require("@/assets/picture07.jpeg"),
      pictureGif07: require("@/assets/picture08.jpeg"),
      hover1: false,
      hover2: false,
      hover3: false,
      hover4: false,
      counter01: 0,
      counter02: 0,
      counter03: 0,
      counter04: 0,
    };
  },
  computed: {
    picture1Hover() {
      if (this.hover1 === true) {
        return this.pictureGif01;
      } else {
        return this.pictureStatic;
      }
    },
    picture2Hover() {
      if (this.hover2 === true) {
        return this.pictureGif02;
      } else {
        return this.pictureGif03;
      }
    },
    picture3Hover() {
      if (this.hover3 === true) {
        return this.pictureGif04;
      } else {
        return this.pictureGif05;
      }
    },
    picture4Hover() {
      if (this.hover4 === true) {
        return this.pictureGif06;
      } else {
        return this.pictureGif07;
      }
    },
  },
};
</script>

<style scoped>
.app {
  display: grid;
  grid-template-columns: 1fr;
  grid-template-rows: auto auto auto;
  grid-template-areas:
    "title"
    "Totallikes"
    "image";
}
img {
  width: 300px;
  height: 500px;
  display: block;
  width: 100%;
  max-width: 400px;
}

body {
  color: rgb(243, 204, 178);
  margin: 0;
  font-family: arial;
  background-color: rgb(243, 204, 178);
}

.title {
  grid-area: title;
  font-size: 2em;
  text-align: center;
  color: salmon;
  font-style: italic;
}
.title {
  animation-duration: 3s;
  animation-name: slidein;
  animation-iteration-count: 1;
  animation-direction: alternate;
}
@keyframes slidein {
  from {
    margin-left: 100%;
    width: 100%;
  }

  to {
    margin-left: 0%;
    width: 100%;
  }
}

.Totallikes {
  grid-area: Totallikes;
  font-size: 2em;
  text-align: center;
  color: rgb(166, 88, 88);
  font-style: italic;
}

.Totallikes:hover {
  background-color: yellow;
}

.image {
  grid-area: image;
  position: relative;
  width: 400px;
}

.image__img {
  display: block;
  width: 100%;
}

.image__overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 15%;
  background: rgba(236, 200, 200, 0.2);
  flex-direction: column;
  align-items: center;
  transition: opacity 0.15s;
}
</style>






