<template>
  <div>
    <div>
      <label>用户名：</label>
      <input type="text" v-model="user.username" />
    </div>
    <div>
      <label>密码：</label>
      <input type="password" v-model="user.password" />
    </div>
    <div>
      <label>年龄：</label>
      <input type="number" v-model="user.age" />
    </div>
    <div>
      <input type="button" value="提交" v-on:click="submit" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user: {
        username: "",
        password: "",
        age: 0
      }
    };
  },
  methods:{
    submit () {
        axios.post("/signup",this.user).then((res)=>{
            alert(JSON.stringify(res.data))
        })
    }
  }
};
</script>

<style>
</style>