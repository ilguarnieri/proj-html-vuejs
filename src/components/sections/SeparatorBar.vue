<template>

    <section class="separator" 
    :class="styleSeparator.bgPattern ? 'bg__pattern' : 'bg__violet' ">
        <div class="container">
            <p>{{styleSeparator.title}}</p>

            <button class="btn">
                <a :href="styleSeparator.link">
                    <span class="btn-text">{{styleSeparator.button}}</span>
                </a>
            </button>
        </div>
    </section>  

</template>


<script>
export default {
    name:'SeparatorBar',

    props:{
        styleSeparator: Object
    }  
}
</script>


<style lang="scss" scoped>
@import '../../assets/scss/_variables.scss';
@import '../../assets/scss/_common.scss';

.separator{    
    color: $white;

    &.bg__pattern{
        background-image: url('../../assets/img/background/pattern.png');
        background-size: cover;
        background-repeat: no-repeat;
    }

    &.bg__violet{
        background-color: $butterfly;
    }

    .container{
        height: 140px;
        display: flex;
        justify-content: space-between;
        align-items: center;
        font-size: min(6vw, 35px);
        gap: 10px;

        .btn{
            @include btn__violet;
            position: relative;
            padding-right: 30px;


            .btn-text::after{
                content: '';
                display: inline-block;
                width: 30px;
                aspect-ratio: 1;
                background-image: url('../../assets/img/icon/slider_next.png');
                background-size: cover;
                position: absolute;
                top: 50%;
                transform: translateY(-50%);
            }
        }
    }
}

</style>