<template>
  <div class="app-container">
    <el-table
      v-loading="listLoading"
      :data="users"
      element-loading-text="Loading"
      border
      fit
      highlight-current-row
    >
      <el-table-column
        prop="id"
        label="ID">
      </el-table-column>
      <el-table-column
        prop="name"
        label="Name">
      </el-table-column>
    </el-table>
  </div>
</template>
<script>
import axios from 'axios'
 export default{
  data () {
    return {
      users: null
    }
  },
  mounted () {
    axios
      .get('http://localhost:3000/users') //ここにURLを入れる
      .then(response => (this.users = response.data))
  }
   }
</script>