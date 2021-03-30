<template>
    <div>
        <Nav />
        <div class="presentation">

            <div class="loader">
                <div class="wrapper">
                    <div class="box"></div>
                </div>
            </div>

            <div class="screen">
                <div class="img-box">
                    <div class="cover-img"></div>
                    <img src="../assets/img/presentation.jpg" alt="">
                </div>
                <div class="title">
                    <h1>M</h1>
                    <h1>A</h1>
                    <h1>R</h1>
                    <h1>K</h1>
                    <h1>H</h1>
                    <h1>A</h1>
                </div>
                <h1 class="text">PHOTOGRAPHER</h1>
                <h1 class="text2">001</h1>
            </div>
        </div>
    </div>
</template>

<script>

import { TimelineLite, Expo, TweenMax } from "gsap";
import Nav from "./Nav.vue";

export default {
    name: 'Home',
    components: {
        Nav
    },

    setup() {
        
    },

    mounted() {
        const loader = new TimelineLite();

        loader.from(".box", 1.2, {
            delay: 1.5,
            y: 200,
            height:"0vh",
            ease: Expo.easeInOut,
        }).to(".box", 1.2, {
            y: -200,
            height: "0vh",
            ease: Expo.easeInOut,
        }).to(".loader", 1, {   
            opacity: 0,
            ease: Expo.easeInOut,
        });
        
        TweenMax.to(".cover-img", 1.5, {
            y: "-100%",
            delay: 3.6,
            ease: Expo.easeInOut,
        })
        TweenMax.staggerFrom(".title h1", 1, {
            y: 50,
            opacity: 0,
            delay: 3.7,
            ease: Expo.easeInOut,
        }, 0.1)
        TweenMax.from(".text, .text2", 1, {
            y: 50,
            opacity: 0,
            delay: 3.9,
            ease: Expo.easeInOut,
        })
    }
}
</script>

<style lang="scss" scoped>

.presentation{
    height: 100vh;
    width: 100vw;
    position: relative;
    overflow: hidden;

    .loader{
        position: absolute;
        background-color: black;
        width: 100%;
        height: 100%;
        display: flex;
        justify-content: center;
        align-items: center;
        z-index: 2;

        .wrapper{
            height: 80%;
            width: 100%;
            overflow: hidden;
            position: relative;

            .box{
                position: absolute;
                height: 20vh;
                width: 5vw;
                background-color: white;
                transform: translate(-50%, -50%);
                top: 50%;
                left: 50%;
            }
        }
    }
    
    .screen{
        display: flex;
        justify-content: center;
        align-items: center;
        position: relative;
        height: 100%;
        width: 100%;

        .img-box{
            height: 100%;
            width: 100%;
            display: flex;
            align-items: center;
            justify-content: center;
            overflow: hidden;
            position: relative;

            .cover-img{
                background-color: white;
                width: 100%;
                height: 100%;
                position: absolute;
            }

            img{
                height: auto;
                width: 30%;    
            }
        }

        .title{
            position: absolute;
            font-size: 7vw;
            display: flex;
            flex-direction: row;
            -webkit-text-fill-color: transparent;
            -webkit-text-stroke-width: 0.15vw;
        }

        .text{
            position: absolute;
            font-size: 1rem;
            bottom: 40px;
            left: 80px;
            text-decoration: underline;
            font-family: monument
        }

        .text2{
            position: absolute;
            font-size: 3rem;
            top: 100px;
            right: 200px;
            font-family: monument
        }
    }
}

</style>