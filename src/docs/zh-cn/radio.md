<script>

export default {
  data: function () {
    return {
      disabled: true,
    }
  },
  methods: {
    _onGroupChange (selectValue) {
        console.log('radio checked:' + selectValue)
        this.groupValue = e.selectValue
      }
  }
}
</script>

# Radio 单选框
单选框

## 何时使用

用于在多个备选项中选中单个状态。和 Select 的区别是：Radio 所有选项默认可见，方便用户在比较中选择，因此选项不宜过多。

## 代码演示

::: demo

<summary>
  #### RadioGroup组合
  一组互斥的 Radio 配合使用。
</summary>

```html
<template>
<v-radio-group
            :on-change="_onGroupChange"
            :radios="[{value: 'a', text: 'A'},{value: 'b', text: 'B'},{value: 'c', text: 'C'},{value: 'd', text: 'D'}]" name="sex">
          </v-radio-group>
</template>
<script>
export default {
    methods: {
      _onGroupChange (selectValue) {
        console.log('radio checked:' + selectValue)
        this.groupValue = e.selectValue
      }
    }
  }
</script>
```
:::

::: demo

<summary>
  #### 不可用
  radio 不可用。
</summary>

```html
<template>
<v-radio-group
            :on-change="_onGroupChange"
            :radios="[{value: 'a', text: 'A',disabled:true},{value: 'b', text: 'B'},{value: 'c', text: 'C'},{value: 'd', text: 'D'}]" name="sex">
          </v-radio-group>
</template>
<script>
export default {
    methods: {
      _onGroupChange (selectValue) {
        console.log('radio checked:' + selectValue)
        this.groupValue = e.selectValue
      }
    }
  }
</script>
```
:::

::: demo

<summary>
  #### 按钮样式及大小
  不同大小及样式,通过value初始化默认选中
</summary>

```html
<template>
<v-radio-group
            :on-change="_onGroupChange"
            type="button" size="small" value="beijing"
            :radios="[{value: 'shanghai', text: 'shanghai'},{value: 'beijing', text: 'beijing',disabled:true},{value: 'chengdu', text: 'chengdu'},{value: 'tianjin', text: 'tianji'}]" name="sex">
          </v-radio-group>
          <br>
          <br>
<v-radio-group
            :on-change="_onGroupChange"
            type="button" value="shanghai" 
            :radios="[{value: 'shanghai', text: 'shanghai'},{value: 'beijing', text: 'beijing',disabled:true},{value: 'chengdu', text: 'chengdu'},{value: 'tianjin', text: 'tianji'}]" name="sex">
          </v-radio-group>
          <br>
          <br>
<v-radio-group
            :on-change="_onGroupChange"
            type="button" size="large" value="shanghai"
            :radios="[{value: 'shanghai', text: 'shanghai'},{value: 'beijing', text: 'beijing',disabled:true},{value: 'chengdu', text: 'chengdu'},{value: 'tianjin', text: 'tianji'}]" name="sex">
          </v-radio-group>
</template>
<script>
export default {
    methods: {
      _onGroupChange (selectValue) {
        console.log('radio checked:' + selectValue)
        this.groupValue = e.selectValue
      }
    }
  }
</script>
```
:::

## API
### radioGroup Props

| 参数      | 说明          | 类型      | 默认值  |
|---------- |-------------- |----------  |-------- |
| size | 组件中点的大小，可选值为 small default large | string | default |
| value | 初始化value控制默认选中 | boolean | 无 |
| type | radio 展示方式，可选button | string | 无 |
| radios | 展示多个radio项,[{value: 'shanghai', text: 'shanghai'},{value: 'beijing', text: 'beijing',disabled:true}]<br>value-radio项的value值，text-radio项展示值，disabled-是否不可用，默认false | json | 无 |

### radioGroup event

| 参数      | 说明          | 类型      | 默认值  |
|---------- |-------------- |----------  |-------- |
| onChange | 选项变化时的回调函数 | Function(selectValue) | 无 |