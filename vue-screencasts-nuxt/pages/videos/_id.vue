<template>
    <div>
        <nuxt-child :video="video" />
    </div>
</template>

<script>
    export default {
        head() {
            return {
                title: '',
                titleTemplate: `%s ${this.video.name} - Vue Screencasts`
            }
        },
        async asyncData({$axios, params}) {
            let response = await $axios.get(`/video/${params.id}`)
            let video = response.data

            return {
               video
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>