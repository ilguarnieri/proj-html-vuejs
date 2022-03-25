<template>
    <section class="education-wrapper">

        <div class="container">
            <div class="education-info">
                <h2 class="title">We have been educating children for over fifteen years. Our goal is to create a place that engages each child.</h2>

                <p class="description">Praesent arcu gravida vehicula est node maecenas loareet morbi a dosis luctus. Urna eget lacinia eleifend praesent luctus a arcu quis facilisis venenatis aenean interdum.</p>

                <CheckList :listitems="listitems" />

            </div>

            <div class="icon-summary">
                ciaodsafsafsasfa

            </div>
        </div>

    </section>    
</template>


<script>
import CheckList from '../commons/CheckList.vue'

export default{
    name:'StyleEducation',

    components:{
        CheckList
    },

    data(){
        return{
            listitems:[
                'Comprehensive reporting on individual achievement',
                'Educational field trips and school presentations',
                'Individual attention in a small-class setting',
                'Learning program with after-school care',
                'Opportunities to carry out scientific investigations',
                'Positive learning environment for your child'
            ]
        }
    }
}
</script>


<style lang="scss" scoped>
@import '../../assets/scss/_variables.scss';

.education-wrapper{
    background-color: $lightgray;

    .container{
        padding: 80px 0;
        display: flex;
        justify-content: space-between;

        .education-info, .icon-summary{
            width: calc(50% - 30px);
        }

        .education-info{

            & > *{
                margin-bottom: 35px;
            }

            & :last-child{
                margin-bottom: 0;
            }

            .title{
                color: $butterfly;

            }

            .description{
                
            }
        }
    }
}

</style>