<template>
    <section>

        <ul class="list-wrapper">
            <li class="list-item" v-for="(item, i) in listitems" :key="i">
                {{item}}
            </li>
        </ul>

    </section>
</template>


<script>

export default {
    name:'CheckList',

    props:{
        listitems:{
            type: Array,
            required: true
        }
    }
}
</script>


<style lang="scss" scoped>
.list-wrapper{

    .list-item{

        &::before{
            content:'';
            display: inline-block;
            width: 17px;
            height: 17px;
            background-image: url('../../assets/img/icon/style_1.png');
            background-repeat: no-repeat;
            background-position: center;
            background-size: cover;
        }
    }
}

</style>