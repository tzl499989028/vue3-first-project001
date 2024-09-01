<template>
  <div>我是测试组件</div>
  <div>{{a}}</div>
  <div>{{b}}</div>

  <div>用户名：<input v-model="userName" type="text"></div>
  <div>密码：<input v-model="password" type="text"></div>
  <button @click="login">login</button>
</template>

<script setup lang="ts">
import {ref} from 'vue'
var a:any = ref('')
var b:any = ref('')
 fetch('http://0.0.0.0:9000/getRequest',{method:'GET'}).then(res=>{
     a.value = res||'get失败'
 })
 const userName = ref('')
 const password = ref('')
 const login=()=>{
     fetch('http://0.0.0.0:9000/login',{method:'POST',body:JSON.stringify({
        userName:userName.value,password:password.value
     })}).then(res=>{
        b.value = res||'post失败'
     })
 }
fetch('http://jsonplaceholder.typicode.com/posts',{method:'GET'})

console.log('a分支修改的内容')

console.log('c分支修改的内容')

console.log('c分支修改的内容002')



</script>

<style></style>
