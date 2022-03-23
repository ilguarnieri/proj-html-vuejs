<template>
    <section>

        <FirstJumbo />
        <SeparatorBar :styleSeparator="separator1"/>

    </section>    
</template>


<script>
import FirstJumbo from '../sections/FirstJumbo.vue'
import SeparatorBar from '../sections/SeparatorBar.vue'

export default {
    name:'FableMain',

    components:{
        FirstJumbo,
        SeparatorBar
    },

    data(){
        return{
            separator1:{
                title: 'How to Enroll Your Child to a Class?',
                button: 'Learn more',
                link: '#',
                bgPattern: false
            },
            separator2:{
                title: 'See Our Kindergarten Photo Gallery!',
                button: 'View gallery',
                link: '#',
                bgPattern: true
            }
        }
    }
}
</script>