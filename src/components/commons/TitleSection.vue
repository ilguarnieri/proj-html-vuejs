<template>
    <section class="section__header">

        <h1 class="title">{{title}}</h1>
        <p class="subtitle">{{subtitle}}</p>

    </section>    
</template>


<script>

export default{
    name: 'TitleSection',

    props:{
        title:{
            type: String,
            require: true
        },
        subtitle:{
            type: String,
            require: true
        }
    }    
}
</script>


<style lang="scss" scoped>
@import '../../assets/scss/_variables.scss';

.section__header{
    text-align: center;

    .title{
        color: $butterfly;
        font-size: min(7.5vw, 45px);
        font-weight: 400;
        margin-bottom: 10px;
    }

    .subtitle{
        color:$gray;
        font-size: min(3.7vw, 17px);

        &::after{
            content: '';
            display: block;
            width: 100%;
            height: 15px;
            padding-top: 30px;
            background-image: url('../../assets/img/icon/header_divider.png');
            background-repeat: no-repeat;
            background-position: center;
            background-size: 90px;
        }
    }
}
</style>