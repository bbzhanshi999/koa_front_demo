<template>
  <div class="home">
    <div>
      <label>用户名：</label>
      <input type="text" v-model="username"/>
    </div>
    <div>
      <label>密码：</label>
      <input type="password" v-model="password"/>
    </div>
    <div>
      <input type="button" value="提交" v-on:click="submit"/>
    </div>
  </div>
</template>

<script>
export default {
  name: 'home',
  data () {
    return {
      username:"",
      password:""
    }
  },
  methods:{
    submit () {
      this.$axios.post('/sigin',{username:this.username,password:this.password}).then((res)=>{
        alert(JSON.stringify(res.data))
      })
    }
  }
}
</script>
