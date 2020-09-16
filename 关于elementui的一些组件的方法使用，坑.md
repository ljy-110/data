关于elementui的一些组件的方法使用，坑

1.el-input现在只能输入数字

```vue
//添加oninput="value=value.replace(/[^\d]/g,'')"
<el-form-item label="邮政编码" prop="zip">
   <el-input clearable oninput="value=value.replace(/[^\d]/g,'')" v-model="ruleForm.zip" placeholder="请输入邮政编码"></el-input>
</el-form-item>
```

