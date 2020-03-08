<template>
  <div class="container sm:mx-auto flex mt-6 sm:justify-between flex-col sm:flex-row">
    <div class="flex mx-auto sm:mx-0 flex-col sm:flex-row ">
      <img class="rounded-full h-20 w-20 self-center" src="@/assets/image/moi.png" alt="">
      <div class="my-auto sm:ml-6 flex flex-col items-center sm:items-start">
        <div class="font-bold text-blue-600">Paul Nallet</div>
        <div>Développeur web</div>
      </div>
    </div>  
    <div class="flex sm:my-auto justify-center  sm:order-none p-4 sm:p-0">
        <nav class="flex px-6 text-blue-600 font-bold">A propos</nav>
        <nav class="flex px-6 text-gray-400">Blog</nav>
    </div>
  </div>
</template>

<script>

export default {
 head () {
    return {
      title: "Bonjour c'est Paul",
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

