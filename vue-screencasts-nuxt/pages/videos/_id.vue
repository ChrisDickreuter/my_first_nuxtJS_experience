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
        
        async asyncData({$axios, params, store}) {
            let response = await $axios.get(`/video/${params.id}`)
            let video = response.data

            store.commit('SET_CURRENT_VIDEO', video)
        },

        computed: {
            video() {
                return this.$store.state.currentVideo
            }
        }

    }
</script>

<style lang="scss" scoped>

</style>