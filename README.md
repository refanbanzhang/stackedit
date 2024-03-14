## 基础使用
| 属性名   | 描述             |
| -------- | ---------------- |
| `open`   | 控制显示         |
| `onOk`   | 确定按钮回调     |
| `onCancel` | 取消按钮回调   |

## 异步关闭
通过在handleOk回调中，异步修改open的值实现。
```js
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
类型为`ReactNode`
当不需要默认底部按钮时，可以设为 `footer={null}`

## 确认对话框
命令式调用弹窗
```js
confirm({
	title: 'Do you want to delete these items?',
	icon: <ExclamationCircleOutlined />,
	content: 'When clicked the OK button, this dialog will be closed after 1 second',
	onOk() {
		return new Promise((resolve, reject) => {
			setTimeout(Math.random() > 0.5 ? resolve : reject, 1000);
		})
		.catch(() => console.log('Oops errors!'));
	},
	onCancel() {},
});
```
`title icon content`均为`ReactNode`
`onOk onCancel`回调，参数为关闭函数，返回`promise`时`resolve`后自动关闭。
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExNzk1NjE5NjAsLTE3NzU0NzY4MzldfQ
==
-->