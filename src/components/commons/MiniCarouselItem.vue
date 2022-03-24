

<style lang="scss" scoped>
@import '../../assets/scss/_variables.scss';

.carousel__item{
    width: 490px;
    height: 360px;
    display: none;
    position: relative;
    user-select: none;

    &.active{
        display: block;
    }

    .arrow__carousel{
        position: absolute;
        top: 50%;
        transform: translateY(-50%);
        width: 100%;
        display: flex;
        justify-content: space-between;

        .arrow__prev, .arrow__next{
            background-color: $orange;
            cursor: pointer;
        }
    }
}

</style>