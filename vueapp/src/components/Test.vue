<template>
    <div class="test">
        <input type="text" v-model="title"><br/>
        <h1>{{title}}</h1>
        <p v-if="showName">{{user.firstName}}</p>
        <p v-else>Nobody</p>
        <ul>
            <li v-for="item in items" :key="item.title">{{item.title}}</li>

        </ul>
        <button v-on:click="greet('Hello world')" >Say Greeting</button>

        <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit">
    
    <label>First Name:</label><input type="text" v-model="user.firstName"><br/> 
    <label>Last Name:</label><input type="text" v-model="user.lastName"><br/> 
    <h3>{{fullname}}</h3>
    <h2>{{msg}}</h2>

    </div>
</template>

<script>
export default {
    name: 'test',
    props:{
        msg:{
            type: String,
            default:'Foobar'
        }
    },
    data() {
        return {
            title: 'Hello World',
            user: {
                firstName: 'John',
                lastName: 'Dow'
            },
            showName: true,
            items: [
                { title: 'item1' },
                { title: 'item2' },
                { title: 'item3' }
            ]
        }
    },
    methods:{
        greet:function(greeting){
            alert(greeting);
        },
        pressKey:function(e){
            console.log(e.target.value);
        },
        enterHit:function(){
            console.log("You hit enter");
        }
    },
    computed:{
        fullname:function(){
            return this.user.firstName+' '+this.user.lastName;
        }
    }
}
</script>


<style scoped>

</style>