<template>

    <section class="slider">

        <!-- img -->
        <SlideDynamic v-for="(object, i) in setImages" :key="i"
        :imageSlide="object" :activeIndex="currentIndex === i ? true : false"/>

        <!-- icon thumb -->
        <div class="thumbnails">

            <div class="thumb" v-for="(objec, index) in setImages" :key="index"
            :class="currentIndex === index ? 'activeThumb' : ''" @click="thumbClick(index)">

            </div>        
        </div>

    </section>
</template>


<script>
import SlideDynamic from '../../components/commons/SlideDynamic.vue'

export default{
    name:'JumboSlides',

    components:{
        SlideDynamic
    },

    data(){
        return{
            currentIndex: 0,
            clock: undefined,
            setImages:[
                {
                    icon:[
                        require('../../assets/img/background/slider_icon1.png'),
                        require('../../assets/img/background/slider_icon2.png'),
                        require('../../assets/img/background/slider_icon3.png'),
                        require('../../assets/img/background/slider_icon5.png'),
                        require('../../assets/img/background/slider_icon7.png'),
                    ],
                    bg: require('../../assets/img/background/slider_slide1_background.png'),
                    imgFocus: require('../../assets/img/photo/slider_slide1_img1.png'),
                    imgBlur: require('../../assets/img/photo/slider_slide1_img2.png')
                },
                {
                    icon:[
                        require('../../assets/img/background/slider_icon16.png'),
                        require('../../assets/img/background/slider_icon14.png'),
                        require('../../assets/img/background/slider_icon11.png'),
                        require('../../assets/img/background/slider_icon12.png'),
                        require('../../assets/img/background/slider_icon13.png'),
                    ],
                    bg: require('../../assets/img/background/slider_slide2_background.png'),
                    imgFocus: require('../../assets/img/photo/slider_slide2_img1.png'),
                    imgBlur: require('../../assets/img/photo/slider_slide2_img2.png')
                },
                {
                    icon:[
                        require('../../assets/img/background/slider_icon15.png'),
                        require('../../assets/img/background/slider_icon11.png'),
                        require('../../assets/img/background/slider_icon17.png'),
                        require('../../assets/img/background/slider_icon16.png'),
                        require('../../assets/img/background/slider_icon18.png'),
                    ],
                    bg: require('../../assets/img/background/slider_slide3_background.png'),
                    imgFocus: require('../../assets/img/photo/slider_slide3_img1.png'),
                    imgBlur: require('../../assets/img/photo/slider_slide3_img2.png')
                }
            ]
        }
    },

    methods:{
        thumbClick: function(i){
            this.currentIndex = i
        },

        click_next: function(){
            this.currentIndex++;
            if(this.currentIndex > this.setImages.length -1){this.currentIndex = 0}
        },

        stop_play: function(){
            clearInterval(this.clock)
        },

        start_play: function(){
            this.clock = setInterval(this.click_next, 3000)
        }
    },

    mounted(){
        this.start_play()
    }
}

</script>


<style lang="scss" scoped>

.slider{
    position: relative;

    .thumbnails{

        display: flex;
        position: absolute;
        bottom: 30px;
        left: 50%;
        gap: 10px;
        height: 20px;

        .thumb{
            content: '';
            height: 11px;
            width: 35px;
            border: 2px solid orange;
            align-self: flex-end;
            cursor: pointer;
        }

        .activeThumb{
            align-self: flex-start;
        }
    }
}
</style>