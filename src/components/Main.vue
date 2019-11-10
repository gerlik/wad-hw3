<template>
    <section id="container">
        <section id="main">
            <div class="content">
                <Profile :class="{active: isActive === 'profile'}"></Profile>
                <Courses :class="{active: isActive === 'courses'}"></Courses>
            </div>
            <div class="controls">
                <button :class="{active: isActive === 'profile'}" @click="isActive = 'profile'" class="pill"
                        id="profile-button">
                    Profile
                </button>
                <button :class="{active: isActive === 'courses'}" @click="isActive = 'courses'" class="pill"
                        id="courses-button">
                    Courses
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
                isActive: 'profile',
            }
        },
    }
</script>

<style scoped>

</style>