<template>
  <section class="h-full flex flex-col">
      <nav class="p-6 text-green-600">Bonjour !  </nav>
      <section class="flex-auto flex flex-row space-around"> 
        <div class=" p-6 text-2xl font-semibold flex " style=" width:30%; min-width:300px ">
            <div class="mt-20">
                🖐 <br>
            Salut moi c'est Paul !
          <br>
          Je suis développeur web <br>
          Je peux vous aider à <br>
          réaliser un projet,<br> 
          donner vie à vos créations <br>
            </div> 
        </div>
        <div class="bg-green-100 flex-auto p-6 text-green-500 text-xl font-semibold">
            <img src="@/assets/image/launch.svg" alt="hero space image"  class="hero-image m-auto">
        </div>
      </section>
      <footer class="flex flex-row flex-wrap">
        <div class="bg-green-500 p-6 text-white text-xl font-semibold text-center add-coffee" style=" width:30%; min-width:300px ">Contactez moi !</div>
        <div class=" flex-auto p-6 text-green-500 text-right"><nuxt-link :to="'/blog'">Blog</nuxt-link> - Podcast - Linkedin </div>
      </footer>
  </section>
</template>

<script>
export default {

}
</script>

<style>
   
   
</style>