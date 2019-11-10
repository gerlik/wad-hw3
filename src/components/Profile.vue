<template>
    <div class="tab" id="profile-container">
        <div id="profile">
            <div class="avatar">
                <img :src="image" alt="My picture" id="picture">
            </div>
            <div class="info">
                <ul>
                    <li id="name">John Doe</li>
                    <li id="birthdate">11/10/1990</li>
                    <li id="faculty">Software Engineering</li>
                </ul>
            </div>
            <div id="gpa">
                <strong>2.75</strong>
            </div>
            <div class="clear-fix"></div>
        </div>
    </div>
</template>

<script>
    export default {
        name: "Profile",
        props: {},
        data: () => {
            return {
                image: require('@/assets/me.png'),
            }
        },
        methods: {}
    }
</script>

<style scoped>

</style>