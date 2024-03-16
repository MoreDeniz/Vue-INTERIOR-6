<template>
    <div>
        <ProjectBanner/>
        <ProjectContent />
    </div>
</template>

<script>
    import ProjectBanner from './ProjectBanner.vue'
    import ProjectContent from './ProjectContent.vue'


    export default {
        name: "ProjectComp",
        components: {
            ProjectBanner,
            ProjectContent,
        }
    }
</script>

<style scoped>

</style>