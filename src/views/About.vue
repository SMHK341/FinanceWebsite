<template>
  <div>
    <section class="hero is-info is-large">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">
            Large title
          </h1>
          <h2 class="subtitle">
            Large subtitle
          </h2>
        </div>
      </div>
    </section>
    <br />
    <div class="columns is-mobile is-centered">
      <div class="column is-8">
        <div class="tile is-ancestor">
          <div class="tile is-parent">
            <FaceCard />
          </div>
          <div class="tile is-parent">
            <FaceCard />
          </div>
          <div class="tile is-parent">
            <FaceCard />
          </div>
        </div>
        <div class="tile is-ancestor">
          <div class="tile is-parent">
            <FaceCard />
          </div>
          <div class="tile is-parent">
            <FaceCard />
          </div>
          <div class="tile is-parent">
            <FaceCard />
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import FaceCard from '@/components/FaceCard.vue'

export default {
  name: 'about',
  components: {
    FaceCard
  }
}
</script>