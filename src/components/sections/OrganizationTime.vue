<template>

    <section class="organization">

        <div class="container">

            <!-- carousel -->
            <MiniCarousel :images="imgCarousel"/>

        </div>

    </section>
    
</template>


<script>
import MiniCarousel from '../commons/MiniCarousel.vue'

export default{
    name:'OrganizationTime',

    components:{
        MiniCarousel
    },

    data(){
        return{
            imgCarousel:[
                require('../../assets/img/photo/gallery_07-690x506.jpg'),
                require('../../assets/img/photo/gallery_01-690x506.jpg'),
                require('../../assets/img/photo/gallery_08-690x506.jpg')
            ]
        }
    }
}
</script>


<style lang="scss" scoped>
@import '../../assets/scss/_variables.scss';

.organization{
    background-color: $bggray;

    .container{
        display: flex;
        justify-content: space-between;
        padding: 75px 10px;

        
    }
}

</style>