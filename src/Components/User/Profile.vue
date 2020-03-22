<template>
    <div>
        <div class="user_profile">
            <h3>User Informations</h3>
            <ul>
                <li><span>Name : </span> {{ name }} </li>
                <li><span>lastName : </span> {{ lastName }} </li>
                <li><span>Age : </span> {{ userAge }} </li>
            </ul>
            <h3>Parents</h3>
            <ul>
                <li v-for="(value, key, index) in userParents " :key="index">
                    <span>
                        {{key}} :
                    </span> 
                    {{ value }} 
                    
                </li>
                
            </ul>
        </div>
        <button @click="updatename">UpdateName</button>
        <button @click="updateage">UpdateAge</button>
        <div>
            <input type="text" v-model="friendInput">
            <button @click="addFriend">AddFriend</button>
        </div>
    </div>
</template>
<script>
import { bus } from "../../main.js";
export default {
    data() {
        return {
            friendInput : ""
        }
    },
    props : {
        name: String,
        lastName: String,
        userAge: Number,
        userParents: Object,

    },
    methods: {
        updatename() {
            this.$emit("updatename", "zinoo")
        },
        updateage() {
            this.$emit("updateage", 22)
        },
        addFriend() {
            bus.$emit( "addFriend", this.friendInput );
        }
    }, 
}
</script>
<style scoped>
    span {
        font-weight: 800;
    }
    .user_profile {
        padding: 10px 20px;
        border: 1px solid #2196f3;
    }
</style>