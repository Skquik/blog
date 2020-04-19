<template>
  <div class="h-full">
    <header-section></header-section>
    <hero-section></hero-section>
  </div>
</template>

<script>
import headerSection from '@/components/header'
import heroSection from '@/components/hero'
export default {
  components:{
    headerSection, 
    heroSection
  },
 head () {
    return {
      title: "Salut moi c'est Paul",
    }
  },
  async asyncData({ error}){
    try{
      // Query to get blog home content
      
    } catch (e) {
      console.log(e)
      // Returns error page
      error({ statusCode: 404, message: 'Page not found' })
    }
  }}
</script>
<style scoped>

</style>

