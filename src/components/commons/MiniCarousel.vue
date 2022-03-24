<template>

    <section class="carousel-wrapper">

        <div class="carousel__slider">
            <div class="carousel__item" v-for="(img, i) in images" :key="i"
            :class="currentIndex === i ? 'active' : '' ">
                <!-- image -->
                <img :src="img">
            </div>

            <!-- arrow -->
            <div class="arrow__carousel">
                <!-- prev -->
                <div class="arrow__prev" @click="clickPre()">
                    <img src="../../assets/img/icon/slider_previous.png">
                </div>
                <!-- next -->
                <div class="arrow__next" @click="clickNext">
                    <img src="../../assets/img/icon/slider_next.png">
                </div>
            </div>
        </div>
        
    </section>
    
</template>


<script>
export default{
    name:'MiniCarousel',

    props:{
        images:{
            type: Array,
            require: true
        }
    },

    data(){
        return{
            currentIndex: 0,
            clock: undefined
        }
    },

    methods:{
        thumbClick: function(i){
            this.currentIndex = i
        },

        clickNext: function(){
            this.currentIndex++;
            if(this.currentIndex > this.images.length -1){this.currentIndex = 0}
        },

        clickPre: function(){
            this.currentIndex = this.currentIndex - 1;
            if(this.currentIndex < 0){this.currentIndex = this.images.length - 1}
        },

        stopPlay: function(){
            clearInterval(this.clock)
        },

        startPlay: function(){
            this.clock = setInterval(this.clickNext, 5000)
        }
    },

    mounted(){
        this.startPlay()
    }
}

</script>


<style lang="scss" scoped>
@import '../../assets/scss/_variables.scss';

.carousel-wrapper{

    .carousel__slider{

        position: relative;

        .carousel__item{
            width: 490px;
            height: 360px;
            display: none;
            
            user-select: none;

            &.active{
                display: block;
            }

            
        }

        .arrow__carousel{
                position: absolute;
                top: 50%;
                transform: translateY(-50%);
                width: 100%;
                display: flex;
                justify-content: space-between;

                .arrow__prev, .arrow__next{
                    background-color: $orange;
                    cursor: pointer;
                }
            }



    }

}


</style>