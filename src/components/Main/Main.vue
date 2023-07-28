<script>
import HistoryAndDate from './components/HistoryAndDate.vue';
import Article from './components/Article.vue';
import News from './components/News.vue'
import SidebarMenu from './components/SidebarMenu.vue';
import Socials from './components/Socials.vue';

export default {
    components: {
        HistoryAndDate,
        Article,
        News,
        SidebarMenu,
        Socials
    }
}
</script>

<template>
    <main class="main container">
        <Socials />
        <HistoryAndDate />
        <section class="main__wrapper">
            <div class="main__wrapper-left">

                <Article />
            </div>
            <aside class="main__wrapper-right" role="complementary">
                <News />
                <SidebarMenu />
            </aside>
        </section>
    </main>
</template>

<style lang='scss' scoped>
.main {
    margin-top: 225px;
    display: flex;
    flex-direction: column;
    padding-bottom: 36px;

    &__wrapper {
        display: flex;

        &-left {
            width: calc(100% - 300px);
        }

        &-right {
            display: flex;
            flex-direction: column;
            gap: 10px;
        }
    }
}


@media (max-width: 1000px) {
    .main {
        margin-top: 145px;
        &__wrapper {

            &-left {
                width: 100%;
            }

            &-right {
                display: none;
            }
        }
    }
}
</style>