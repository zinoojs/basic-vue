<template>
    <div>
        <app-header></app-header>
        <div class="container">
            <comUserProfile 
            :name = "name"
            :lastName = "lastName"
            :userAge = "userAge"
            :userParents = "parents"
            @updatename = "name = $event"
            @updateage = "userAge = $event"
            />
        <comFriends/>
        <comHabilities>
            <div slot="hab">
                <ul>
                    <li v-for="( hab, index ) in habilities" :key="index"> {{ hab }} </li>
                </ul>
            </div>
            <div slot="test">
                <p>Hello Test user slot</p>
            </div>
            <hr>
            <a href="#">This is a link</a>
            <hr>
            <div :slot="testslot">
                changing slot is changing
            </div>
            
        </comHabilities>
        </div>
        <comFooter/>
    </div>
</template>
<script>
import comFooter from './Components/Header_Footer/Footer';
import comUserProfile from './Components/User/Profile';
import comFriends from './Components/User/Friend';
import comHabilities from './Components/User/Habilities';
export default {
    data(){
        return {
            name : "bobo",
            lastName : "koko",
            userAge : 30,
            parents : {
                mother : "Daw Mya",
                father : "U Hla"
            },
            habilities : [ 'one', 'two', 'three' ],
            testslot : '',
        }
    },
    
    components: {
        comFooter,
        comUserProfile,
        comFriends,
        comHabilities
    },
    created() {
        setTimeout(()=>{
            this.testslot = "otherone"
        }, 3000 )
    }
}
</script>
<style scoped>
    body {
        margin: 0;
        padding: 0;
    }
    .container {
        box-sizing: border-box;
        min-height: 80vh;
        padding: 20px;
    }
</style>