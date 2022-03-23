<template>
    <section class="header__menu">

        <ul class="menu__list">
            <li v-for="(el, i) in store.menu" :key="i" class="menu__item"
            @mouseenter="el.active = true" @mouseleave="el.active = false">

                <a :href="el.link" :class="store.activeIndex == i ? 'active' : ''">

                    <!-- item icon -->
                    <div class="icon__item"
                    :style="el.active || store.activeIndex == i ?
                    {backgroundImage: `url(${el.iconHover})`} : {backgroundImage: `url(${el.icon})`}"></div>

                    <!-- title item -->
                    <p>{{el.text}}</p>
                </a>
                       
            </li>                    
        </ul>

        <div class="hamburger__icon">
            <font-awesome-icon icon="fa-bars" />
        </div>

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
    }    
}
</script>


<style lang="scss" scoped>
@import '../../assets/scss/_variables.scss';

.header__menu{
    color: $textHeader;
    display: flex;
    align-items: center;  

    .menu__list{
        display: contents;

        .menu__item a{
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            gap: 20px;
            height: 120px;
            user-select: none;

            .icon__item{
                margin: 0 30px;
                height: 32px;
                aspect-ratio: 1;
                background-repeat: no-repeat;
                background-position: center;
                background-size: contain;
            }

            &:hover, &.active{
                background-color: $itemMenuHover;
                color: $textHeaderHover;
            }
        }
    }

    .hamburger__icon{
        font-size: 32px;
        display: none;
        cursor: pointer;
    }
}

@media screen and (max-width: 850px) {

    .header__menu{

        .menu__list{
            display: none;
        }

        .hamburger__icon{
            display: block;
        }
    }    
}
</style>