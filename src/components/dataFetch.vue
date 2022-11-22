<template>
    <div>
        <h2>Fetch data by using fake api</h2>
        <table>
            <tr>
                <th>Id</th>
                <th>title</th>
                <th>url</th>
                <th>thumbnailUrl</th>
                <!-- <th>address</th> -->
            </tr>
            <tr v-for="item in list" :key="item.id">
                <td>{{item.id}}</td>
                <td>{{item.title}}</td>
                <td>{{item.url}}</td>
                <!-- <td>{{item.email}}</td> -->
                <td>{{item.thumbnailUrl}}</td>
            </tr>
        </table>
    </div>
</template>

<script>

  import Vue from 'vue'
  import axios from 'axios'
  import VueAxios from 'vue-axios'
  Vue.use(VueAxios,axios)
    export default{
        name : 'dataFetch'
        ,data(){
            return{
                list:undefined
            }
        },
        mounted(){
        fetch('https://jsonplaceholder.typicode.com/photos?_limit=4')
        .then(resp => resp.json())
        .then(data => this.list = data)
  }
    }
</script>