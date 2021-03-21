<template>
<body>
  <div class="container">
    <form id="form" class="form">
      <h2>注册</h2>
      <div class="form-control">
        <label for="username">姓名</label>
        <input type="text" id="username" placeholder="请输入用户名" @blur="checkName()">
        <small>错误提示</small>
      </div>
      <div class="form-control">
        <label for="email">邮箱</label>
        <input type="text" id="email" placeholder="请输入邮箱" @blur="checkEmail()">
        <small>错误提示</small>
      </div>
      <div class="form-control">
        <label for="password">密码</label>
        <input type="password" id="password" placeholder="请输入密码">
        <small>错误提示</small>
      </div>
      <div class="form-control">
        <label for="password2">确认密码</label>
        <input type="password" id="password2" placeholder="请输入用户名">
        <small>错误提示</small>
      </div>
      <button>提交</button>
    </form>
  </div>
</body>
</template>
<script>
export default {
  name: 'projectOne',
  data () {
    return {
      msg: '登录页',
      nums: [ 1, 2, 3, 4 ]
    }
  },
  methods: {
    test () {
      alert('ssss')
    },
    checkName () {
      if ((document.getElementById('username').value).trim() === '') {
        alert('此项为必填')
      }
    },
    checkEmail () {
      const re = /^([A-Za-z0-9_\-.])+@([A-Za-z0-9_\-.])+.([A-Za-z]{2,4})$/
      if ((document.getElementById('email').value).trim() === '') {
        alert('此项为必填')
      } else {
        if (!re.test((document.getElementById('email').value).trim())) {
          alert('邮箱格式错误')
        }
      }
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import 'style.css';
</style>
