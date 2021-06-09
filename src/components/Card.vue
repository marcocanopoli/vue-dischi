<template>
    <div>
        <img :src="imgUrl" :alt="author + title">
        <h2>{{ upperCaseTitle }}</h2>
        <h3>{{ author }}</h3>
        <span>{{ year }}</span>
    </div>
</template>

<script>
export default {
    name: 'Card',
    props: {
        title: String,
        author: String,
        year: String,
        imgUrl: String
    },
    data() {
        return {
            upperCaseTitle : this.title.toUpperCase()
        }
    }
}
</script>

<style lang="scss" scoped>
    @import '../style/variables.scss';

    div {
        height: 380px;
        width: 200px;
        padding: $cardMargin;
        margin-bottom: $cardMargin;
        background-color: $secondColor;
        text-align: center;        

        img {
            height: 150px;
            width: 150px;
            margin-bottom: $cardMargin;
            object-fit: cover;
            object-position: center;
        }

        h2 {
            font-size: 22px;            
            margin-bottom: $cardMargin;
        }

        h3,
        span {
            font-weight: 400;
            color: scale-color($textColor, $lightness: -40%);
        }
    }
</style>