<template>
  <div class="home">
    <VideoHeader title="Investment done right." subtitle="Company Name"/>
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <Transactions/>
    <Footer/>
  </div>
</template>

<script>
// @ is an alias to /src
import VideoHeader from '@/components/VideoHeader.vue'
import HelloWorld from '@/components/HelloWorld.vue'
import Transactions from '@/components/Transactions.vue'
import Footer from '@/components/Footer.vue'

export default {
  name: 'home',
  components: {
    VideoHeader,
    HelloWorld,
    Transactions,
    Footer
  }
}
</script>
