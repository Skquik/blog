<template>
  <section class="h-full flex flex-col">
      <nav class="p-6 text-green-600">Welcome ! 🖐 </nav>
      <section class="flex-auto flex flex-row"> 
        <div class=" p-6 text-2xl font-semibold" style=" width:30%; min-width:300px ">Salut moi c'est Paul.
          <br>
          Je peux vous aider si <br>
          vous  souhaitez réaliser un projet,<br> 
          donner vie à vos créations <br>
        
        </div>
        <div class="bg-green-100 flex-auto p-6 text-green-500 text-xl font-semibold">Salut moi c'est aussi paul,</div>
      </section>
      <footer class="flex flex-row flex-wrap">
        <div class="bg-green-500 p-6 text-white bold" style=" width:30%; min-width:300px ">Contactez moi !</div>
        <div class=" flex-auto p-6 text-green-500"><nuxt-link :to="'/blog'">blog</nuxt-link> - podcast - linkedin </div>
      </footer>
  </section>
</template>

<script>

export default {

 head () {
    return {
      title: "Salut moi c'est Paul",
    }
  },
  data(){
      return{
        text:"", 
        textToDisplay:"Bonjour je suis le texte"
      }
  },
  async asyncData({error}){
    try{
      // Query to get blog home content

    } catch (e) {
      console.log(e)
      // Returns error page
      error({ statusCode: 404, message: 'Page not found' })
    }
  }}
</script>

<style lang="css">
html, body, #__layout, #__nuxt, #__layout > div{
    height: 100vh;
}

</style>

