<template>
  <div id="app">
    <dynamic-form
      v-model="data"
      ref="dynamic-form"
      :languages="languages"
      :descriptors="descriptors">
      <template slot="operations">
        <el-button @click="reset">Reset</el-button>
        <el-button type="primary" @click="validate" plain>Validate</el-button>
      </template>
    </dynamic-form>
  </div>
</template>

<script>
import { Button } from 'element-ui'
import DynamicForm from '../packages/dynamic-form/index'
import descriptors from './descriptor'

export default {
  name: 'app',
  components: {
    DynamicForm,
    ElButton: Button
  },
  data () {
    return {
      data: {},
      descriptors,
      languages: {
        en_US: {
          addKeyPlaceholder: 'just for test',
          addKeyButtonText: 'Add',
          addArrayItemButtonText: 'Add'
        },
        zh_TW: {
          addKeyPlaceholder: '輸入想增加的名稱',
          addKeyButtonText: '增加',
          addArrayItemButtonText: '增加'
        }
      }
    }
  },
  watch: {
    'data.string' (value) {
      if (value) {
        this.descriptors.object.fields.string.hidden = true
      }
    }
  },
  methods: {
    reset () {
      this.$refs['dynamic-form'].resetFields()
    },
    validate () {
      this.$refs['dynamic-form'].validate()
    }
  },
  created () {}
}
</script>

<style lang="scss">
html, body {
  margin: 0;
  padding: 0;
}
#app {
  padding: 20px;
}
</style>
