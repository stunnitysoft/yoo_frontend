<template>
    <vs-row vs-w="12" class="events">
    <div class="main-header">
        <span class="left">Upcoming Events</span> <span class="right">view all</span>
    </div>
    <div class="center">
       <span @click="slideLeft"> <i class="fas fa-angle-left icon icon-left"></i></span>
        <div class="slider" id="slider">
         <div class="event-card">
             <div class="event-image">
                 <img src="../assets/image/EAP.jpg" alt="EAP">
                 <span class="free">Free</span>
             </div>
             <div class="event-header">
                 East African Party
             </div>
             <div class="loc-time">
                 <div class="location">kicukiro, kigali</div>
                 <div class="time">27<sup>th</sup> jun</div>
             </div>

         </div>
         <div class="event-card">
             <div class="event-image">
                 <img src="../assets/image/EAP.jpg" alt="EAP">
             </div>
             <div class="event-header">
                 East African Party
             </div>
             <div class="loc-time">
                 <div class="location">kicukiro, kigali</div>
                 <div class="time">27<sup>th</sup> jun</div>
             </div>

         </div>
         <div class="event-card">
             <div class="event-image">
                 <img src="../assets/image/EAP.jpg" alt="EAP">
             </div>
             <div class="event-header">
                 East African Party
             </div>
             <div class="loc-time">
                 <div class="location">kicukiro, kigali</div>
                 <div class="time">27<sup>th</sup> jun</div>
             </div>

         </div>
         <div class="event-card">
             <div class="event-image">
                 <img src="../assets/image/EAP.jpg" alt="EAP">
             </div>
             <div class="event-header">
                 East African Party
             </div>
             <div class="loc-time">
                 <div class="location">kicukiro, kigali</div>
                 <div class="time">27<sup>th</sup> jun</div>
             </div>

         </div>
         <div class="event-card">
             <div class="event-image">
                 <img src="../assets/image/EAP.jpg" alt="EAP">
             </div>
             <div class="event-header">
                 East African Party
             </div>
             <div class="loc-time">
                 <div class="location">kicukiro, kigali</div>
                 <div class="time">27<sup>th</sup> jun</div>
             </div>
         </div>
     </div>
        <span @click="slideRight"><i class="fas fa-angle-right icon icon-right"></i></span>
    </div>
    </vs-row>
</template>
<script>
 import anime from 'animejs'
 import {mapMutations,mapState} from 'vuex'

 export default {
     name: 'upComingEvents',
     components: {},
     data() {
         return {
             name: 'this name'
         }
     },
     computed: {
         ...mapState(["myTranslateX"])
     },
     methods: {
         ...mapMutations(["CHANGE_TRANSLATE_X"]),
         slideLeft: (e) => {
             anime({
                 targets: ".slider",
                 translateX: "-=300px"
             });
             console.log(this.myTranslateX);
             this.CHANGE_TRANSLATE_X(e)
         },
         slideRight: (e) => {
             anime({
                 targets: ".slider",
                 translateX: "+=300px"
             });
             this.CHANGE_TRANSLATE_X(e)
         }
     }
 }
</script>

<style lang="scss" scoped>
    @import "src/assets/scss/main";
    $photo-width:300px;

    .main-header{
        padding: 0 10em;
        text-align: left;
        .left{
            font-size: 1.3em;
        }
    }

    .center {
        width:90%;
        margin: auto;
        overflow: hidden;
        position: relative;

        .icon{
            position: absolute;
            top: 50%;
            background: white;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            z-index: 2;
            &:hover{
                box-shadow: 0 0 14px $blue18-1-rgba;
            }

            &-left{
                left: 0;
            }
            &-right{
                right: 0;
            }
        }

        .slider{
            width: 1700px;
            height: 290px;

        }
    }
    .events{
        background-color: lighten($blue18-5-rgba,12%);
        padding: 1em;
        display: block !important;

        h2{
            font-family: $raleway;
            display: block;
        }

        .event-card{
                grid-template-rows: auto 50px 50px;
                grid-template-columns: $photo-width;
                position: relative;
                font-family: $work-sans;
                background-color: white;
                width: $photo-width;
                display: inline-block;
                margin:1em;
                padding: 0 0 1em 0;
            &:hover{
                transition: all .3s ease;
                box-shadow: 0 0 20px 0px lighten($blue18-1-rgba,20%);
                width: calc($photo-width + 10px);
            }

            .event-image{
                position: relative;
                .free{
                    position: absolute;
                    background: white;
                    padding: .5em 1em ;
                    z-index: 1;
                    top:1px;
                    right: 2px;
                    border-radius: .5em;
                    box-shadow: lighten($blue18-5-rgba,10%);
                }
                img{
                    width:$photo-width;
                    position: relative;
                }
            }
            .event-header{
                margin: .6em 0;
                text-align: left;
                font-weight: 700;
                font-size: 1.5em;
                padding: 0 .5em;
            }
            .loc-time{
                display: grid;
                padding: 0 .5em;
                grid-template-columns: 6fr 4fr;
                .location{
                    text-align: left;
                }
                .time{
                    text-align: right;
                    color: $Cool-Orange;
                }
            }
        }
    }
</style>