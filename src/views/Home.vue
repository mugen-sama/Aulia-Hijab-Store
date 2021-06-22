<template>
  <div class="home">
    <!-- <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <HeaderAulia />
    <HeroAulia />
    <WomenBannerAulia />
    <InstaAulia />
    <PartnerLogoAulia />
    <FooterAulia />
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import HeaderAulia from '@/components/HeaderAulia.vue'
import HeroAulia from '@/components/HeroAulia.vue'
import WomenBannerAulia from '@/components/WomenBannerAulia.vue'
import InstaAulia from '@/components/InstaAulia.vue'
import PartnerLogoAulia from '@/components/PartnerLogoAulia.vue'
import FooterAulia from '@/components/FooterAulia.vue'



export default {
  name: 'Home',
  components: {
    HeaderAulia,
    HeroAulia,
    WomenBannerAulia,
    InstaAulia,
    PartnerLogoAulia,
    FooterAulia

  }
}
</script>
