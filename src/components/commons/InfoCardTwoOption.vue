<template>
    <section class="info">

        <h2 class="info__title">{{info.title}}</h2>

        <div v-for="(option, i) in info.options" :key="i" class="info__description">
            <div class="option__img">
                <img :src="option.icon">
            </div>

            <div class="option__card">
                <h3 class="option__title">{{option.title}}</h3>
                <p class="option__description">{{option.description}}</p>
            </div>
        </div>

    </section>    
</template>


<script>

export default{
    name: 'InfoCardTwoOption',

    props:{
        info:{
            info: Array,
            required: true
        }
    }
}

</script>


<style lang="scss" scoped>
@import '../../assets/scss/_variables.scss';

.info{
    color: $butterfly;

    .info__title{
        margin-bottom: 30px;
        font-size: min(6vw, 27px);
    }

    .info__description{
        display: flex;
        justify-content: space-between;
        align-items: flex-start;
        gap: 30px;

        .option__img{
            flex-grow: 1;
            background-color: $orange;
            border-radius: 50%;
            display: flex;
            justify-content: center;
            align-items: center;
            min-width: 70px;
            aspect-ratio: 1;
            user-select: none;

            img{
                width: 30px;
            }
        }

        .option__card{
            margin-bottom: 25px;

            .option__title{
                margin-bottom: 15px;
                font-size:  min(5.2vw, 20px);
            }

            .option__description{
                color: $gray;
                font-size: 15px;
               
            }
        }
    }
}
</style>