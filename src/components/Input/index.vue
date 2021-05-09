<script>
import { Input,Form } from 'ant-design-vue'
import { uuid } from 'vue-uuid';
export default {
  name: 'hs-inputs',
  props:['name','defaultValue','allowClear','size','placeholder','label',"labelCol","wrapperCol",'itemLayout','styles','decorators',"disabled","rules"],
  data () {
    return {
      visible: false
    }
  },
  mounted () {
  },
  methods:{
    handleChange(e){
      this.$emit('change', e.target.value)
    }
  },
  render () {
    const {
      name,
      size,
      placeholder,
      label,
      itemLayout,
      styles,
      required,
      decorators,
      disabled,
      rules,
      allowClear,
      defaultValue
    } = this._props
    return (
      <Form.Item label={label} labelCol={itemLayout?itemLayout.labelCol:7} wrapperCol={itemLayout?itemLayout.wrapperCol:17}>
        <Input
          key={"uuid"}
          size={size||'small'}
          disabled={disabled?disabled:false}
          v-decorator={[
            name,
            {rules:rules,initialValue:defaultValue}
          ]}
          allowClear={allowClear?allowClear:false}
          placeholder={placeholder?placeholder:"请输入"+label}
          style={styles?styles:{width:"100%"}}
          defaultActiveFirstOption={false}
          showArrow={false}
          filterOption={false}
          onChange={this.handleChange}
          notFoundContent={null}
        />
      </Form.Item>
    )
  }
}
</script>
