<template>
    <section class="header__menu">

        <ul>
            <li v-for="(el, i) in store.menu" :key="i" class="menu__item"
            @mouseenter="el.active = true" @mouseleave="el.active = false">

                <a :href="el.link" :class="store.activeIndex == i ? 'active' : ''">
                    <div class="icon__item"
                    :style="el.active || store.activeIndex == i ?
                    {backgroundImage: `url(${el.iconHover})`} : {backgroundImage: `url(${el.icon})`}"></div>
                    <p>{{el.text}}</p>
                </a>
                       
            </li>                    
        </ul>

    </section>    
</template>


<script>
import store from '../../store.js'

export default{
    name: 'MenuList',

    data(){
        return{
            store
        }
    },

    
}
</script>


<style lang="scss" scoped>
.header__menu{
    color: #554E9E;
    display: flex;

    ul{
        display: contents;

        .menu__item a{
            padding: 25px;
            display: flex;
            flex-direction: column;
            gap: 20px;

            .icon__item{
                height: 32px;
                aspect-ratio: 1;
                background-repeat: no-repeat;
                background-position: center;
                background-size: contain;
            }

            &:hover, &.active{
                background-color: orange;
                color: white;
            }

        }

        




    }
}

</style>