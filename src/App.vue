<template>
  <div id="app">

    <router-view/>
  </div>
</template>

<script>
 import axios from 'axios'
 export default {
        data: function () {
            return {
                loadData(pramas) {
                    return axios.get("static/datatable.json",pramas).then(res =>{
                        return res.data;
                    });
                },
                columns:[
                    {title:"歌名",field:'name'},
                    {title:"时长",field:'time'},
                    {title:"歌手",field:'singer'},
                    {title:"专辑",field:'album'},
                ]
            }
        },
        methods:{
            
        }
    }
</script>


