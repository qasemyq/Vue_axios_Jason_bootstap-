<template>
<div class='container'>
    <h3>GG and Vue</h3>
    <table class="table table-dark">
    <thead>
        <tr>
        <th scope="col">Id</th>
        <th scope="col">Name</th>
        <th scope="col">Email</th>
        <th scope="col">City</th>
        </tr>
    </thead>
    <tbody>
        <tr v-for= "item in users" v-bind:key="item.id">
        <th scope="row">{{item.id}}</th>
        <td>{{item.name}}</td>
        <td>{{item.email}}</td>
        <td>{{item.address.city}}</td>
        </tr>
    </tbody>
    </table>
    </div>
</template>

<script>
//
import axios from 'axios';
export default {
    name: "Users",
    data () {
        return{
            users: null,
        };
    },
    created: function () {
        axios.get('https://jsonplaceholder.typicode.com/users').then(res => {
            this.users = res.data;
        })
    }
}
</script>

<style>
 h3 {
     margin-bottom: 20px;
 }
</style>
