<template>
    <section>

        <FirstJumbo />
        <SeparatorBar :styleSeparator="separator1"/>
        <WelcomeSection />

    </section>    
</template>


<script>
import FirstJumbo from '../sections/FirstJumbo.vue'
import SeparatorBar from '../sections/SeparatorBar.vue'
import WelcomeSection from '../sections/WelcomeSection.vue'

export default {
    name:'FableMain',

    components:{
        FirstJumbo,
        SeparatorBar,
        WelcomeSection
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