<template>
  <div >
    <hooper :autoPlay="true" :playSpeed="10000" class="transactions">
      <slide>
        <img src="https://d2qfyj0q2n9d96.cloudfront.net/uploads/2018/10/our-customers-logos.png" alt="transactions"/>
      </slide>
      <slide>
        <img src="https://d2qfyj0q2n9d96.cloudfront.net/uploads/2018/10/our-customers-logos.png" alt="transactions"/>
      </slide>
      <hooper-pagination slot="hooper-addons"></hooper-pagination>
    </hooper>
  </div>
</template>

<script>
  import { Hooper, Slide, Pagination as HooperPagination } from 'hooper';
  import 'hooper/dist/hooper.css';

export default {
  name: 'Transactions',
  components: {
    Hooper,
    Slide,
    HooperPagination
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.transactions {
  height: 500px;
}
</style>

