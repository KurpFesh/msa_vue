<template>
    <article class="header__article">
        <h1 class="header__article--title">{{description.title}}</h1>
        <p class="header__article--description">{{description.text}}</p>
        <!-- <span class="link-detailed--description">подробнее</span> -->
        
        <ul class="information__list" v-if="description.links">
            <li class="information__list--page" v-for="link in description.links" :key="link.to">
                <a :href="link.to">{{link.text}}</a>
            </li>
        </ul>
    </article>
</template>

<script>
export default {
    props: {
        description: {
            title: String,
            text: String,
        },
    }
}
</script>

<style scoped lang="scss">
    .header__article{
        position: absolute;
        left: 0;
        bottom: 0;
        width: 445px;
        height: 445px;
        box-sizing: border-box;
        background-color: #0059bd;
        &--title{
            margin: 3rem auto 0 auto;
            width: 80%;
            min-height: 150px;
            font-family: 'Montserrat',sans-serif;
            font-size: 46px;
            line-height: 56px;
            font-weight: 400;
            color: #FFFFFF;
        }
        &--description{
            margin: 0 auto;
            width: 80%;
            min-height: 152px;
            padding-bottom: 52px;
            padding-right: 40px;
            font-family: 'Montserrat',sans-serif;
            font-size: 18px;
            line-height: 26px;
            font-weight: 300;
            color: #FFFFFF;
        }
    }

    .link-detailed--description{
        padding-left: 23px;
        font-family: 'Montserrat',sans-serif;
        font-size: 18px;
        line-height: 24px;
        font-weight: 500;
        color: #FFFFFF;
    }

    .information__list{
        height: 60px;
        display: flex;
        flex-direction: column;
        flex-wrap: wrap;

        &--page{
            padding-right: 20px;
            text-align: left;
            font-family: 'Montserrat',sans-serif;
            font-size: 15px;
            line-height: 30px;
            font-weight: 300;
            color: #FFFFFF
        }
    }
</style>