<template>
    <div class="user_profile">
        <h3>User Profile</h3>
        <div>
            <slot name="hab"></slot>
            <hr>
            <slot name="test"></slot>
        </div>
        <slot></slot>
        <hr>
        <slot name="otherone">Loading ... ...</slot>
    </div>
</template>
<script>
export default {
    // data() {
    //     return {
    //         habilities : [ 'one', 'two', 'three' ]
    //     }
    // }
}
</script>
<style scoped>
    .user_profile {
        padding: 10px 20px;
        border: 1px solid #2196f3;
    }
    li {
        color: red;
        list-style: none;
    }
</style>