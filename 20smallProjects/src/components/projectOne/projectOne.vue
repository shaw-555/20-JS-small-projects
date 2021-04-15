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
        <input type="password" id="password" placeholder="请输入密码" @blur="checkLength()">
        <small>错误提示</small>
      </div>
      <div class="form-control">
        <label for="password2">确认密码</label>
        <input type="password" id="password2" placeholder="请输入用户名" @blur="matchPassWord()">
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
        let nodeList = document.querySelectorAll('.form-control')
        nodeList.forEach((i) => {
          document.querySelector('.form-control').classList.add('error')
        })
      }
    },
    checkEmail () {
      // 你会
      const re = /^([A-Za-z0-9_\-.])+@([A-Za-z0-9_\-.])+.([A-Za-z]{2,4})$/
      if ((document.getElementById('email').value).trim() === '') {
        alert('此项为必填')
      } else {
        if (!re.test((document.getElementById('email').value).trim())) {
          alert('邮箱格式错误')
          let nodeList = document.querySelectorAll('.form-control')
          nodeList.forEach((i) => {
            document.querySelector('.form-control').classList.add('error')
          })
        }
      }
    },
    checkLength () {
      const min = 10
      const max = 20
      const value = document.getElementById('password').value
      if (value.trim().length < min || value.trim().length > max) {
        alert(`密码应当大于${min}个字符且小于${max}个字符`)
      } else {
        console.log('密码合法')
      }
    },
    matchPassWord () {
      const value1 = document.getElementById('password').value
      const value2 = document.getElementById('password2').value
      value1 === value2 ? console.log('两次密码一样') : alert('两次密码不相同11111111111')
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
@import 'style.css';
</style>
