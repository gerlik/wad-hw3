<template>
    <div class="tab" id="courses-container">
        <h1 class="title">Courses</h1>
        <table id="courses">
            <thead>
            <tr>
                <th>#</th>
                <th>Course Title</th>
                <th>Semester</th>
                <th>Grade</th>
            </tr>
            </thead>
            <tbody>
                <tr v-for="course in course_list" :key="course.id">
                    <td>{{course.id}}</td>
                    <td>{{course.title}}</td>
                    <td>{{course.semester}}</td>
                    <td>{{course.grade}}</td>
                </tr>
            </tbody>
        </table>
        <br>
        <br>
        <div>
            <button @click="toggleAddCourse = !toggleAddCourse" class="blue-button" id="add-course-button">+</button>
            <span id="add-course" v-if="toggleAddCourse">
                <input class="input" id="title" placeholder="Course title" type="text" v-model="title">
                <input class="input" id="semester" max="8" min="1" placeholder="Semester" type="number"
                       v-model="semester">
                <input class="input" id="grade" max="100" min="0" placeholder="Grade" type="number"
                       v-model="grade">
                <button @click="add" class="green-button" id="save-course">Save</button>
                <button @click="cancel" class="grey-button" id="cancel-course">Cancel</button>
            </span>
        </div>
    </div>
</template>

<script>
    //import Course from "./models/Course";

    import Course from "../models/Course";

    export default {
        name: "Courses",
        components: {},
        props: {
            course_list: Array,
        },
        data: () => {
            return {
                toggleAddCourse: false,
                title: '',
                semester: '',
                grade: '',
                course: Object,
            }

        },
        methods: {
            cancel: function () {
                this.title = '';
                this.semester = '';
                this.grade = '';
                this.toggleAddCourse = false;
            },

            add: function () {
                this.course_list.push(new Course(this.course_list.length+1, this.title, this.semester, this.grade));
                this.cancel()
            }
        }
    }
</script>

<style scoped>

</style>