<template>
    <section id="container">
        <section id="main">
            <div class="content">
                <Profile :toggle-tab="toggleTab"></Profile>
                <Courses :toggle-tab="toggleTab"></Courses>
            </div>
            <div class="controls">
                <button :class="{active:pillActive}" @click="toggleTab" class="pill" id="profile-button">Profile
                </button>
                <button :class="{active:pillActive}" @click="toggleTab" class="pill" id="courses-button">Courses
                </button>
            </div>
        </section>
    </section>
</template>


<script>
    import Profile from './Profile.vue'
    import Courses from './Courses.vue'

    export default {
        name: "Main",
        components: {
            Profile,
            Courses
        },
        data: () => {
            return {
                pillActive: true,
            }
        },
        props: {
            toggleTab: Function
        },
        methods: {}
    }
</script>

<style scoped>

</style>