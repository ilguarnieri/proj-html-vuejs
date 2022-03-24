<template>
    <section>

        <FirstJumbo />
        <SeparatorBar :styleSeparator="separator1"/>
        <WelcomeSection />
        <OrganizationTime />
        <ClassSection />

        <!-- education section -->

        <GallerySection />
        <SeparatorBar :styleSeparator="separator2"/>

        <!-- second jumbo slider -->
        <!-- whats new -->

        <GeoMap />
        <FableFooter />

    </section>    
</template>


<script>
import FirstJumbo from '../sections/FirstJumbo.vue'
import SeparatorBar from '../sections/SeparatorBar.vue'
import WelcomeSection from '../sections/WelcomeSection.vue'
import OrganizationTime from '../sections/OrganizationTime.vue'
import ClassSection from '../sections/ClassSection.vue'

import GallerySection  from '../sections/GallerySection.vue'
import GeoMap from '../sections/GeoMap.vue'
import FableFooter from '../macro/FableFooter.vue'

export default {
    name:'FableMain',

    components:{
        FirstJumbo,
        SeparatorBar,
        WelcomeSection,
        OrganizationTime,
        ClassSection,

        GallerySection,
        GeoMap,
        FableFooter
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