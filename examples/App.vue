<template>
  <div id="app">
    <div class="button">
      <h2>按钮2</h2>
      <div class="row">
        <h3>普通按钮</h3>
        <tq-button>button</tq-button>
        <tq-button type="primary">primary</tq-button>
        <tq-button type="success">success</tq-button>
        <tq-button type="info">info</tq-button>
        <tq-button type="warning">warning</tq-button>
        <tq-button type="danger">danger</tq-button>
      </div>
      <div class="row">
        <h3>拟态按钮</h3>
        <tq-button mimicry>button</tq-button>
        <tq-button type="primary" mimicry>primary</tq-button>
        <tq-button type="success" mimicry>success</tq-button>
        <tq-button type="info" mimicry>info</tq-button>
        <tq-button type="warning" mimicry>warning</tq-button>
        <tq-button type="danger" mimicry>danger</tq-button>
      </div>

      <div class="row">
        <h3>朴素按钮</h3>
        <tq-button plain>button</tq-button>
        <tq-button type="primary" plain>primary</tq-button>
        <tq-button type="success" plain>success</tq-button>
        <tq-button type="info" plain>info</tq-button>
        <tq-button type="warning" plain>warning</tq-button>
        <tq-button type="danger" plain>danger</tq-button>
      </div>

      <div class="row">
        <h3>圆角按钮</h3>
        <tq-button round>button</tq-button>
        <tq-button type="primary" round>primary</tq-button>
        <tq-button type="success" round>success</tq-button>
        <tq-button type="info" round>info</tq-button>
        <tq-button type="warning" round>warning</tq-button>
        <tq-button type="danger" round>danger</tq-button>
      </div>
      <div class="row">
        <h3>圆形按钮</h3>
        <tq-button circle :icon="['far', 'smile']"> </tq-button>
        <tq-button type="primary" circle :icon="['far', 'edit']"> </tq-button>
        <tq-button type="success" circle :icon="['fas', 'check']"> </tq-button>
        <tq-button type="info" circle :icon="['far', 'envelope']"> </tq-button>
        <tq-button type="warning" circle :icon="['far', 'star']"> </tq-button>
        <tq-button type="danger" circle :icon="['far', 'trash-alt']">
        </tq-button>
      </div>
      <div class="row">
        <h3>禁用按钮</h3>
        <tq-button plain disabled>button</tq-button>
        <tq-button type="primary" disabled>primary</tq-button>
        <tq-button type="success" disabled>success</tq-button>
        <tq-button type="info" disabled>info</tq-button>
        <tq-button type="warning" disabled>warning</tq-button>
        <tq-button type="danger" disabled>danger</tq-button>
      </div>
      <div class="row">
        <h3>文字加图标按钮</h3>
        <tq-button :icon="['far', 'smile']">button</tq-button>
        <tq-button type="primary" :icon="['far', 'edit']">primary</tq-button>
        <tq-button type="success" :icon="['fas', 'check']">success</tq-button>
        <tq-button type="info" :icon="['far', 'envelope']">info</tq-button>
        <tq-button type="warning" :icon="['far', 'star']">warning</tq-button>
        <tq-button type="danger" :icon="['far', 'trash-alt']">danger</tq-button>
      </div>
      <div class="row">
        <h3>点击事件</h3>
        <tq-button type="primary" @click="sayHello">say hello</tq-button>
      </div>
    </div>
    <div class="dialog">
      <tq-button type="primary" @click="dialogVisiable = true"
        >显示对话框</tq-button
      >
      <tq-dialog title="tip" top="200px" :visiable.sync="dialogVisiable">
        <template v-slot:title>
          <span>提示</span>
        </template>

        <span>这是一段信息</span>
        <template v-slot:footer>
          <tq-button @click="dialogVisiable = false">取消</tq-button>
          <tq-button type="primary" @click="dialogVisiable = false"
            >确定</tq-button
          >
        </template>
      </tq-dialog>
    </div>
    <div class="input">
      <h2>输入框</h2>
      <div class="row">
        <h3>基本输入框</h3>
        <tq-input placeholder="请输入内容"></tq-input>
      </div>
      <div class="row">
        <h3>文本域输入框</h3>
        <tq-input placeholder="写点什么" type="textarea"></tq-input>
      </div>
      <div class="row">
        <h3>禁用</h3>
        <tq-input placeholder="请输入内容" disabled></tq-input>
      </div>
      <div class="row">
        <h3>可清除</h3>
        <tq-input
          placeholder="请输入内容"
          type="text"
          name="username"
          v-model="username"
          clearable
        ></tq-input>
      </div>
      <div class="row">
        <h3>密码可见</h3>
        <tq-input
          placeholder="请输入内容"
          type="password"
          name="password"
          v-model="password"
          show-password
        ></tq-input>
      </div>
    </div>
    <!-- v-model相当于:value=xxx和@input="xxx=e.target.value" -->
    <div class="switch">
      <h2>Switch</h2>
      <div class="row">
        <h3>基本Switch</h3>
        <tq-switch v-model="switchActive"></tq-switch>
      </div>
      <div class="row">
        <h3>自定义颜色</h3>
        <tq-switch
          v-model="switchActive"
          activeColor="skyblue"
          inactiveColor="orange"
          name="paied"
        ></tq-switch>
        <div class="row">
          <h3>禁用</h3>
          <tq-switch v-model="switchActive" disabled></tq-switch>
        </div>
        <div class="row">
          <h3>拟态</h3>
          <tq-switch v-model="switchActive" mimicry></tq-switch>
        </div>
        <div class="row">
          <h3>change事件</h3>
          <tq-switch
            v-model="switchActive"
            activeColor="skyblue"
            @change="handleChange"
          ></tq-switch>
        </div>
      </div>
    </div>
    <div class="radio">
      <h2>单选框</h2>
      <div class="row">
        <h3>基本样式</h3>
        <tq-radio label="1" v-model="gender" name="male">男</tq-radio>
        <tq-radio label="2" v-model="gender" name="female">女</tq-radio>
      </div>
      <div class="row">
        <h3>自定义颜色</h3>
        <tq-radio label="1" v-model="gender" name="male" color="green"
          >男</tq-radio
        >
        <tq-radio label="2" v-model="gender" name="female" color="pink"
          >女</tq-radio
        >
      </div>
      <div class="row">
        <h3>拟态</h3>
        <tq-radio label="1" v-model="gender" name="male" mimicry>男</tq-radio>
        <tq-radio label="2" v-model="gender" name="female" mimicry>女</tq-radio>
      </div>
      <div class="row">
        <h3>radio组</h3>
        <tq-radio-group v-model="gender">
          <tq-radio label="1" name="male">男</tq-radio>
          <tq-radio label="2" name="female">女</tq-radio>
        </tq-radio-group>
      </div>
    </div>
    <div class="checkout">
      <h2>复选框</h2>
      <div class="row">
        <h3>基础样式</h3>
        <tq-checkbox name="read" label="1" v-model="checkboxChoice"></tq-checkbox>
      </div>

      <div class="row">
        <h3>自定义颜色</h3>
        <tq-checkbox
          name="read"
          label="1"
          v-model="checkboxChoice"
          activeColor="orange"
        ></tq-checkbox>
      </div>
      <div class="row">
        <h3>拟物样式</h3>
        <tq-checkbox
          name="read"
          label="1"
          v-model="checkboxChoice"
          mimicry
        ></tq-checkbox>
      </div>
      <div class="row">
        <h3>禁用</h3>
        <tq-checkbox
          name="read"
          label="1"
          v-model="checkboxChoice"
          disabled
        ></tq-checkbox>
      </div>
    </div>
    <div class="checkboxGroup">
      <h2>复选框组</h2>
      <div class="row">
        <tq-checkbox-group v-model="checkedArray">
          <tq-checkbox name="apple" label="1">苹果</tq-checkbox>
          <tq-checkbox name="banana" label="2">香蕉</tq-checkbox>
          <tq-checkbox name="peach" label="3">桃子</tq-checkbox>
        </tq-checkbox-group>
      </div>
    </div>

    <div class="formItem">
      <h2>表单项</h2>
      <!-- <div class="row">
        <tq-form-item label="活动">
          <tq-input name="username"></tq-input>
        </tq-form-item>
      </div> -->
      <tq-form :model="form" label-width="80px">
        <tq-form-item label="用户名">
          <tq-input name="username" v-model="form.name"></tq-input>
        </tq-form-item>
        <tq-form-item label="邮箱">
          <tq-input name="email" v-model="form.email"></tq-input>
        </tq-form-item>
      </tq-form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dialogVisiable: false,
      username: 'Joey',
      password: '123456',
      switchActive: false,
      gender: '1',
      checkboxChoice: false,
      checkedArray: ['1', '3'],
      form: {
        name: 'Joey',
        email: 'Joey@mail.com',
        labelwidth: '80px'
      }
    }
  },
  methods: {
    sayHello() {
      window.alert('hello')
    },
    closeDialog(value) {
      this.dialogVisiable = value
    },
    handleChange(value) {
      alert(`change switch to ${value}`)
    }
  }
}
</script>

<style lang="scss">
.row {
  margin-bottom: 20px;
  .tq-button {
    margin-right: 10px;
  }
}
.input {
  & .tq-input {
    width: 18vw;
  }
}

.formItem {
  .tq-input {
    width: 20vw;
  }
}
</style>
