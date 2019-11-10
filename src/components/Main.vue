<template>
    <section id="container">
        <section id="main">
            <div class="content">
                <Profile :user="user" :gpa="gpa_funciton()" :class="{active: isActive === 'profile'}"></Profile>
                <Courses :course_list="course_list" :class="{active: isActive === 'courses'}"></Courses>
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
                user: Object,
                course_list: Array,
                }
            },
        props: {
            user: Object,
            course_list: Array,
            },
        methods: {
            toggleTab: function () {

                if (this.isActive !== !this.isActive) {
                    this.isActive = !this.isActive;
                }
            },
            gpa_funciton: function () {
                var courses = this.course_list;
                var total = 0;
                for (var i = 0; i < courses.length; i++) {
                    let grade = courses[i].grade;
                    if (grade > 90) {
                        total += 4;
                    }
                    else if (grade > 80) {
                        total += 3;
                    }
                    else if (grade > 70) {
                        total += 2;
                    }
                    else if (grade > 60) {
                        total += 1;
                    }
                    else if (grade > 50) {
                        total += 0.5;
                    }
                }
                return (total/i).toFixed(2)
            }

        }
    }
</script>

<style scoped>

</style>