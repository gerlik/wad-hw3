<template>
    <section id="container">
        <section id="main">
            <div class="content">
                <Profile :class="{'active': isActive}"></Profile>
                <Courses :class="{'active': !isActive}"></Courses>
            </div>
            <div class="controls">
                <button :class="{'active':isActive}" @click="toggleTab" class="pill" id="profile-button">Profile
                </button>
                <button :class="{'active':!isActive}" @click="toggleTab" class="pill" id="courses-button">Courses
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
                isActive: true,
            }
        },
        props: {},
        methods: {
            toggleTab: function () {

                if (this.isActive !== !this.isActive) {
                    this.isActive = !this.isActive;
                }
            }

        }
    }
</script>

<style scoped>

</style>