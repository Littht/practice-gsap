<template>
<div class="container">
        <div class="container_cards">
            <div class="cards" :data-index="0">By Email</div>
            <div class="cards" :data-index="1">By Phone</div>
            <div class="cards" :data-index="2">By Post</div>
            <div class="cards" :data-index="3">By Smoke Signal</div>
        </div>
        <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolorem perferendis aliquam minima, saepe temporibus, iusto est ullam sapiente quae voluptatibus aperiam laborum exercitationem. Hic rerum odit, nobis et nesciunt nam.</p>
        <div class="container_btn">
            <button class="main_btn">ALGO</button>
            <button class="main_btn">ALGO2</button>
        </div>
        <div class="circle_btn">A</div>
        <div class="rotate"></div>
</div>
</template>

<script>
import gsap from 'gsap'
import { onMounted } from 'vue'
    export default{
    setup(){
        onMounted(() => {
            gsap.fromTo(
                ".container_cards",
                {
                    opacity: 0,
                    x: -100
                },
                {
                    duration: 1.5,
                    opacity: 1,
                    x: 0,
                },
            ),
            gsap.fromTo(
                "p",
                {
                    opacity:0,
                    x: "-100%"
                },
                {
                    duration: 1.5,
                    opacity:1,
                    x:0,
                    delay: .8,
                    ease:"back.out(1)"
                }
            )
            gsap.fromTo(
                ".main_btn",
                {
                    opacity: 0,
                    y: -20,
                },
                {
                    duration: 1.5,
                    opacity: 1,
                    y: 0,
                    delay: 1.3,
                    ease: "power3.inOut",
                    stagger: 0.1,
                }
            );
            gsap.fromTo(
                ".circle_btn",
                {
                    opacity: 0,
                    y: "100%",
                },
                {
                    duration: 1.5,
                    opacity: 1,
                    y: 0,
                    delay: 2,
                    ease: "power3.inOut",
                    onComplete: () => {
                        gsap.to(".circle_btn", {
                        y: 20,
                        duration: 1,
                        ease: "sine.easeInOut",
                        repeat: -1,
                        yoyo: true,
                        });
                    },
                }
            );
            gsap.fromTo(
                ".rotate",
                {
                    rotation: 0,
                    opacity: 0,
                },
                {
                    duration: 3,
                    opacity: 1,
                    y: 0,
                    ease: "power3.inOut",
                    delay: 3,
                    onComplete: () =>{
                        gsap.to(".rotate",{
                            duration:10,
                            rotate: 360,
                            repeat: -1,
                            yoyo:true
                        })
                    }
                }
            )
        })   
    }
}
</script>

<style scoped>
.container{
    width: 100%;
    display:flex;
    align-items: center;
    flex-direction: column;
    gap: 10px;
}

.container_cards{
    display: flex;
    width: 40%;
    flex-wrap:wrap;
    flex-direction: row;
    gap: 10px;
    margin-bottom: 50px;
}

.cards{
    width: 180px;
    height: 180px;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-grow: 1;
    background-color: white;
    box-shadow: 1px 1px 4px rgba(0, 0, 0, 0.226);
    border-radius: 5px;
}

p{
    width: 70%;
}

.container_btn{
    display: flex;
    gap: 5px;
}

.main_btn{
    padding: 10px;
}

.circle_btn{
    width: 50px;
    height: 50px;
    border-radius: 100%;
    background-color: white;
    display:flex;
    justify-content: center;
    align-items: center;
    border:2px solid #3d3d3d;
    position:absolute;
    left: 10px;
    top: 350px;
}

.rotate{
    position: absolute;
    right: 100px;
    top: 150px;
    height: 300px;
    width: 200px;
    background-color: white;
    border:2px solid #3d3d3d;
}

</style>