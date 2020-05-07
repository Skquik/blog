<template>
  <section class="h-full">
    <div class="h-full bg-blue-300">
      <div class="skewed"></div>
    </div>
  </section>
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
<style scoped>

  .skewed {
    position: absolute;
    top: 0;
    bottom: 0;
    z-index: 0;
    right: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background: #2c3e50;
    transform: skewY(6deg);
    transform-origin: top right;
  }
  .hero-section{
    color: white;
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    font-weight: bolder;
  }
  
  .bottom-section{
    color: white;
    position: absolute;
    bottom: 0;
    left: 0;
    right: 0;
    font-weight: bolder;
    height: 3rem;
    border-radius: 50px 50px 0px 0px ;
    background-color: white;
  }

  .typewriter {
  overflow: hidden; /* Ensures the content is not revealed until the animation */
  border-right: .15em solid orange; /* The typwriter cursor */
  white-space: nowrap; /* Keeps the content on a single line */
  margin: 0 auto; /* Gives that scrolling effect as the typing happens */

  animation: 
    typing 3.5s steps(40, end),
    blink-caret .75s step-end infinite;
}

/* The typing effect */
@keyframes typing {
  from { width: 0 }
  to { width: 100% }
}

/* The typewriter cursor effect */
@keyframes blink-caret {
  from, to { border-color: transparent }
  50% { border-color: orange; }
}
</style>

