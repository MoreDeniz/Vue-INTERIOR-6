<template>
    <div class="home center">
        <HomeBanner />
        <HomeProject />
        <HomeCounter />
        <HomeBlog  />

    </div>
</template>

<script>
    import HomeBanner from './HomeBanner.vue'
    import HomeProject from './HomeProject.vue'
    import HomeCounter from './HomeCounter.vue'
    import HomeBlog from './HomeBlog.vue'



    export default {
        name: "HomeComp",
        components: {
            HomeBanner,
            HomeProject,
            HomeCounter,
            HomeBlog, 
        }
    }
</script>

<style scoped>
    * {
        margin: 0;
        padding: 0;
    }
    .center {
        padding-left: calc(50% - 600px);
        padding-right: calc(50% - 600px);
    }
    .home{
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 96px;
    }
</style>