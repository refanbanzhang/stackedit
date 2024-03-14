## 基础使用
open 控制显示
onOk 确定按钮回调
onCancel 取消按钮回调

## 异步关闭
通过在handleOk回调中，异步修改open的值实现。
```
<Modal
	title="Title"
	open={open} visible
	confirmLoading={confirmLoading}
	onOk={handleOk} 确定按钮
	onCancel={handleCancel} 取消按钮
>
	<p>{modalText}</p>
</Modal>
```

## 自定义页脚
通过传递`footer` 覆盖默认的页脚。
类型为·
底部内容，当不需要默认底部按钮时，可以设为 `footer={null}`
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE2NDAzNDg3MzYsLTE3NzU0NzY4MzldfQ
==
-->