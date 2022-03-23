<template>

    <div class="slide__animation" :style="{backgroundImage: `url(${imageSlide.bg})`}"
    :class="activeIndex ? 'active' : '' ">

        <div class="bg__icon">
            <img  v-for="(icon, i) in imageSlide.icon" :key="i"
            :src="icon" :class="`icon-${i}`">
        </div>

        <div class="play__child" :style="{backgroundImage: `url(${imageSlide.imgBlur})`}">
            <img :src="imageSlide.imgFocus" alt="">
        </div>

    </div>
    
</template>


<script>

export default{
    name:'SlideDynamic',

    props:{
        imageSlide:{
            type: Object,
            require: true
        },
        activeIndex: Boolean
    }
}

</script>


<style lang="scss" scoped>

.slide__animation{
    min-height: 650px;


    display: none;


    background-repeat: repeat-x;
    background-size: contain;
    position: relative;
    user-select: none;
    padding-top: 30px;
    overflow-x: hidden;

    .bg__icon{
        position: relative;
        left: 50%;
        transform: translateX(-80%);
        display: flex;
        align-items: flex-start;
        width: 400px;
        height: 160px;
        z-index: 0;

        & > *{
            width: 80px;    
        }

        .icon-1, .icon-3{
            align-self: flex-end;
        }

        .icon-4{
            margin-left: 20px;
            align-self: center;
        }
    }

    .play__child{
        position: absolute;
        left: 50%;
        top: 0;
        transform: translateX(-10%);        
        width: 770px;
        height: 100%;
        display: flex;
        align-items: center;
        background-repeat: no-repeat;
        background-position: center right;
    }

    &.active{
        display: block;
    }
}

@media screen and(max-width:700px) {

    .slide__animation{

        min-height: 350px;

        .bg__icon{
        transform: translateX(-50%);
        justify-content: center;
    }
        
        .play__child{
            background-size: 0;
            width: 0;
        }
    }    
}

@media screen and(max-width:450px) {

    .icon-0, .icon-4{
        display: none;
    }

      
}

</style>