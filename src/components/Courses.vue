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
            <tr>
                <td>1</td>
                <td>Agile software development</td>
                <td>1</td>
                <td>82</td>
            </tr>
            <tr>
                <td>2</td>
                <td>System modeling</td>
                <td>1</td>
                <td>85</td>
            </tr>
            <tr>
                <td>3</td>
                <td>Object-oriented programming</td>
                <td>2</td>
                <td>99</td>
            </tr>
            <tr>
                <td>4</td>
                <td>Estonian language Level A2</td>
                <td>2</td>
                <td>65</td>
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
                <button class="green-button" id="save-course">Save</button>
                <button @click="cancel" class="grey-button" id="cancel-course">Cancel</button>
            </span>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Courses",
        data: () => {
            return {
                toggleAddCourse: false,
                title: '',
                semester: '',
                grade: '',
            }

        },
        methods: {
            cancel: function () {
                this.title = '';
                this.semester = '';
                this.grade = '';
                this.toggleAddCourse = false;
            }
        }
    }
</script>

<style scoped>

</style>