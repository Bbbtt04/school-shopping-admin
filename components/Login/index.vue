<template>
  <div class="login_wrapper">
    <div class="login_content">
      <div class="left">
        <div class="title">农大小商城后台</div>
        <div class="bottom">
          <img src="@/assets/images/illustration.png" alt="desc" />
        </div>
      </div>
      <div class="right">
        <div class="chose_model">
          <span class="by_password">账号密码登录</span>
        </div>
        <el-form :model="formData" size="large" :rules="rules">
          <el-form-item prop="phone"
            ><el-input
              placeholder="请输入手机号"
              v-model="formData.phone"
            ></el-input
          ></el-form-item>
          <el-form-item prop="password"
            ><el-input
              placeholder="请输入密码"
              v-model="formData.password"
              show-password
            ></el-input
          ></el-form-item>
          <el-form-item>
            <el-button>登录</el-button>
          </el-form-item>
        </el-form>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { FormRules } from 'element-plus'

interface IFormData {
  phone: string
  password: string
}

const formData: IFormData = reactive({
  phone: '',
  password: '',
})
const rules = reactive<FormRules<IFormData>>({
  phone: [{ required: true, message: '请输入手机号', trigger: 'blur' }],
  password: [{ required: true, message: '请输入密码', trigger: 'blur' }],
})
</script>

<style scoped lang="less">
.el-button {
  width: 100%;
}
.login_wrapper {
  width: 100vw;
  height: 100vh;
  background: url('@/assets/images/背景@2x.png') no-repeat;
  background-size: cover;
  display: flex;
  align-items: center;
  justify-content: center;
  .login_content {
    width: 975px;
    height: 620px;
    display: flex;
    .left {
      width: 422px;
      border-radius: 31px 0 0 31px;
      background-color: #f4f4f4;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      .title {
        font-size: 26px;
        font-weight: bold;
        color: #242424;
      }
      .bottom {
        width: 376px;
        height: 280px;
        margin-top: 140px;
        img {
          width: 100%;
          height: 100%;
        }
      }
    }
    .right {
      flex: 1;
      border-radius: 0 31px 31px 0;
      background-color: #fff;
      padding: 130px 70px;
      .chose_model {
        font-size: 18px;
        font-weight: bold;
        margin-bottom: 32px;
        span {
          position: relative;
          z-index: 100;
          &::before {
            content: '';
            position: absolute;
            width: 100%;
            height: 50%;
            background-color: skyblue;
            bottom: 0;
            z-index: -10;
          }
        }
      }
    }
  }
}
</style>
