<template>
    <div class="tab" id="profile-container">
        <div id="profile">
            <div class="avatar">
                <img :src="image" alt="My picture" id="picture">
            </div>
            <div class="info">
                <ul>
                    <li id="name">{{user.firstname + ' ' + user.lastname}}</li>
                    <li id="birthdate">{{user.birthdate}}</li>
                    <li id="faculty">{{user.faculty}}</li>
                </ul>
            </div>
            <div id="gpa">
                <strong>{{gpa}}</strong>
            </div>
            <div class="clear-fix"></div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Profile",
        props: {
            user: Object,
            gpa: Number,
        },
        data: () => {
            return {
                image: require('@/assets/me.png'),
            }
        },
    }
</script>

<style scoped>

</style>