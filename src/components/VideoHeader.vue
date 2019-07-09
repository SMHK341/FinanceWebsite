<template>
  <div>
    <header>
      <div class="overlay"></div>
      <video playsinline autoplay loop muted class="wrapper__video">
        <source src="../assets/video.mp4">
      </video>
      <div class="container">
          <h1 class="title is-1">{{ title }}</h1>
          <h2 class="title is-3">{{ subtitle }}</h2>
      </div>
    </header>
  </div>
</template>

<script>
export default {
  name: 'VideoHeader',
  props: {
    title: String,
    subtitle: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

header {
  position: relative;
  background-color: black;
  height: 60vh;
  min-height: 25rem;
  width: 100%;
  overflow: hidden;
}

header video {
  position: absolute;
  top: 50%;
  left: 50%;
  min-width: 100%;
  min-height: 100%;
  width: auto;
  height: auto;
  z-index: 0;
  -ms-transform: translateX(-50%) translateY(-50%);
  -moz-transform: translateX(-50%) translateY(-50%);
  -webkit-transform: translateX(-50%) translateY(-50%);
  transform: translateX(-50%) translateY(-50%);
  object-fit: cover;
}

header .overlay {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  background-color: black;
  opacity: 0.5;
  z-index: 1;
}

header .container {
  position: relative;
  z-index: 2;
  top: 20vh;
  color: white;
}

</style>
