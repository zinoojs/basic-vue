<template>
    <div class="user_friends">
        <h3>Friends</h3>
        <ul>
            <li v-for="(friend, index) in friends" :key="index">
                {{ friend }}
            </li>
        </ul>
    </div>
</template>
<script>
import { bus } from "../../main.js"
export default {
    data() {
        return {
            friends : [ 'koko', 'momo']
        }
    },
    created() {
        bus.$on( "addFriend", ( value ) => {
            this.friends.push( value );
        })
    }
}
</script>
<style scoped>
    .user_friends {
        padding: 10px 20px;
        border: 1px solid #2196f3;
    }
</style>