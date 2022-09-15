<template>
  <div class="about">
    <transition
     appear
     @before-enter="before"
     @enter="enter"
    >
      <h1>This is an about page</h1>
    </transition>
  </div>
</template>

<script>
  import gsap from 'gsap'
  
  export default{
    setup() {
      const before = (el) =>{
        el.style.transform = 'translateY(-60px)'
        el.style.opacity= 0
      }
      const enter = (el) =>{
        gsap.to(el,{
          duration:1,
          y:0,
          opacity:1,
          ease: 'bounce.out',
        })
      }
      return {before, enter}
    }
  }
</script>
