<template>
  <v-tree :data="treeData" :async="getData" show-line  @select="selectFn" @check="checkFn"></v-tree>
</template>

<script>
import Axios from 'axios'
export default {

  data() {
    return {
      treeData: []
    }
  },
  created() {
      this.initZKTree()
  },
  methods: {
    initZKTree() {
        var api="/api/zkmonitor/allzkNodes"
        this.$axios.get(api,{
            params: {
        "zkNodePath": '/'
    }
        })
        .then((response) =>{
            this.treeData = response.data;
        });
    },
    getData() {

    },
    selectFn(data) {
      console.log(data);
    },
    checkFn(data) {
      console.log(data);
    },
  }
}
</script>