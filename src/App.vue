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
                    {title:"序号",field:'name'},
                    {title:"主机",field:'time'},
                    {title:"端口",field:'singer'},
                    {title:"状态",field:'album'},
                ]
            }
        },
        methods:{
            
        }
    }
</script>


