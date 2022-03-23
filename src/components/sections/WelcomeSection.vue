<template>
    <section class="container">

        <TitleSection
        title="Welcome to Fable"
        subtitle="Fable daycare, preschool, and kindergarten" />

    </section>    
</template>


<script>
import TitleSection from '../commons/TitleSection.vue'

export default{
    name: 'WelcomeSection',

    components:{
        TitleSection,

    }
}
</script>


<style lang="scss" scoped>
.container{
    padding: 60px 10px;
}

</style>