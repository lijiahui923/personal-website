<template>
<div id="login" v-if="show">
    <div class="form-wrap">
        <div class="login-header">Login</div>
        <el-form :model="form" :rules="form_rules" ref="form" label-position="left" class="login-form">
            <el-form-item prop="name">
                <el-input class="loginInput" v-model="form.name" placeholder="USERNAME" clearable></el-input>
            </el-form-item>
            <el-form-item prop="password">
                <el-input class="loginInput" type="password" autocomplete="new-password" v-model="form.password" placeholder="PASSWORD" clearable></el-input>
            </el-form-item>
            <el-form-item>
                <el-button class="login-btn" style="width: 100%" :disabled="submit_disabled" @click="submitForm('form')">Login</el-button>
            </el-form-item>
        </el-form>
        <div class="msg">
            Don't have account?<router-link class="msg-a" to="/">Sign Up</router-link>
        </div>
    </div>
</div>
</template>

<script>
import sha1 from "js-sha1";
import { validate_email, validate_password } from "@/utils/validate";
import { GetCode, Register, Login } from "@/api/login";
import { getToken, setToken, setUsername } from "@/utils/cookies";
export default {
  name: "Login",
  data(){
      /**
         * 自定义检验规则
         */
        // 检验邮箱
        const validate_name_rules = (rule, value, callback) => {
            let regEmail = validate_email(value);
            if (value === "") {
                callback(new Error("请输入邮箱"));
            } else if(!regEmail) {
                callback(new Error("邮箱格式不正确"));
            } else {
                callback();
            }
        }
        // 检验密码
        const validate_password_rules = (rule, value, callback) => {
            let regPassword = validate_password(value);
            let passwords_value = this.form.passwords;
            if (value === "") {
                callback(new Error("请输入密码"));
            } else if(!regPassword){
                callback(new Error("请入 >=6 并且 <= 20 位的密码，包含数字、字母"));
            } else if(passwords_value && passwords_value !== value) {
                callback(new Error("两次密码不一致，请重新输入"));
            } else {
                callback();
            }
        }
        // 检验验证码
        const validate_code_rules = (rule, value, callback) => {
            if (value === "") {
                callback(new Error("请输入验证码"));
            } else if(value.length !== 6) {
                callback(new Error("请输入长度为6位数的验证码"));
            } else {
                callback();
            }
        }
        // 检验规则
        return {
            activeName:'login',
            show: false,
            form: {
                name: "",
                password: "",
                passwords: "",
                code: ""
            },
            code_text: "获取验证码",
            code_loading: false,
            code_disabled: false,
            timer: null,
            submit_disabled: true,
            form_rules: {
                name: [ 
                    { validator: validate_name_rules, trigger: 'blur' }
                ],
                password: [
                    { validator: validate_password_rules, trigger: 'blur' }
                ],
                code: [
                    { validator: validate_code_rules, trigger: 'blur' }
                ]
            }
        }
  },
  beforeMount(){
      this.show = getToken() ? false : true
  },
  methods: {
    // 倒计时
    countdown(number){
      let second = number;
      // 禁用按钮
      this.code_disabled = true;
      // 按钮文本
      this.code_text = `倒计进${second}秒`;
      this.timer = setInterval(() => {
        second--;
        this.code_text = `倒计进${second}秒`;
        if(second < 0) {
          this.code_text = `重新获取`;
          // 启用按钮
          this.code_disabled = false;
          clearInterval(this.timer);
        }
      }, 1000)
    },
    // 获取验证码方法
    getCodeFn(){
        if(this.form.name === "") {
            this.$message.error("邮箱不能为空！！");
            return false;
        }
        if(!validate_email(this.form.name)) {
            this.$message({
                message: "邮箱格式有误，请重新输入！！",
                type: "error"
            })
            return false;
        }
        let requestData = {
            username: this.form.name,
            module: "login"
        };
        this.code_text = "发送中";
        this.code_loading = true;
        GetCode(requestData).then(response => {
            this.$message({
                message: response.message,
                type: "success"
            })
            // 激活按钮
            this.submit_disabled = false;
            // 清除加载
            this.code_loading = false;
            // 执行倒计时方法
            this.countdown(60);
        }).catch(error => {
            this.code_text = "重新获取";
            this.code_loading = false;
        })
    },
    // 提交表单
    submitForm(formName) {
        this.$refs[formName].validate((valid) => {
            // 表单验证通过
            if (valid) {
                // 三元运算
                this.login()
            } else {
                console.log('error submit!!');
                return false;
            }
        })
    },
    // 登录
    login(){
        const requestData = {
            username: this.form.name,
            password: sha1(this.form.password),
            code: this.form.code
        }
        Login(requestData).then(response => {
            const data = response.data
            this.$message({
                message: response.message,
                type: "success"
            })
            setUsername(data.username);
            setToken(data.token);
            this.show = false;
        })
    },
    handleClick () {}
  }
};
</script>
<style lang="scss" scoped>
#login {
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    @include webkitA(background,linear-gradient(to right, #fbc2eb,#a6c1ee));
    font-family: 'Open Sans Light';
    // 增加字符之前的空白
    letter-spacing: .05em;
}
.form-wrap {
  width: 350px;
  height: 500px;
  display: flex;
  flex-direction: column;
  align-items: center;
  background: #fff;
  border-radius: 15px;;
}
.login-header {
    font-size: 30px;
    font-weight: 700;
    line-height: 200px;
} 
.login-form {
    width: 80%;
    margin-bottom: 30px;
}
.login-btn {
    color: #fff;
    @include webkitA(background,linear-gradient(to left, #fbc2eb,#a6c1ee));
}
.msg-a {
    padding-left: 10px;
    color: #a6c1ee;
}
</style>
<style lang="scss">
.el-message.el-message--success { z-index: 100000 !important; }
.login-btn .el-button.is-disabled, .el-button.is-disabled:focus, .el-button.is-disabled:hover {
    outline: none;
    @include webkitA(background,linear-gradient(to left, #fbc2eb,#a6c1ee));
}
</style>