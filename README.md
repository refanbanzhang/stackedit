## 基础使用
| 属性名   | 描述             |
| -------- | ---------------- |
| `open`   | 控制显示         |
| `onOk`   | 确定按钮回调     |
| `onCancel` | 取消按钮回调   |

## 异步关闭
通过在`handleOk`回调中，异步修改`open`的值实现。
```js
<Modal
	title="Title"
	open={open}
	confirmLoading={confirmLoading}
	onOk={handleOk} 确定按钮
	onCancel={handleCancel} 取消按钮
>
	<p>{modalText}</p>
</Modal>

const handleOk = () => {
	setTimeout(() => {
		setOpen(false)
	}, 1000)
}
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

## 信息提示
各种类型的信息提示，只提供一个按钮用于关闭。
```js
Modal.info({
	title: 'This is a notification message',
	content: (
		<div>
			<p>some messages...some messages...</p>
			<p>some messages...some messages...</p>
		</div>
	),
	onOk() {},
});
```

## 国际化
通过自定义文字实现国际化
```
okText="确认"
cancelText="取消"
```

## 手动更新和移除
```js
const modal = Modal.success({
	title: 'This is a notification message',
	content: `This modal will be destroyed after ${secondsToGo} second.`,
});

# 更新弹窗内容
modal.update({
	content: `This modal will be destroyed after ${secondsToGo} second.`,
});

# 手动移除弹窗
modal.destroy();

# 全局移除弹窗（无差别移除）
Modal.destroyAll();
```

## 自定义宽度
```js
<Modal
	width={1000}
>
	<p>some contents...</p>
	<p>some contents...</p>
	<p>some contents...</p>
</Modal>
```
`width {string | number}`

## 拖拽
借助`react-draggable`实现
https://stackblitz.com/edit/react-yuftzi?file=demo.js

## 使用 hooks 获得上下文
解决了什么问题？
解决弹层`content`中需要访问调用处数据的需求。
但是也可以直接在调用处通过`props`传递进来，好像更简单些。
https://stackblitz.com/edit/react-zvzpjz?file=demo.js,Detail.js
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTg4ODk2MjI2OCw4MDM5MDMwOTAsMTk2Nj
gzNTk4NSwtMzE5MjY0MjI3LDE5OTU2NTQzNTEsLTE3NzU0NzY4
MzldfQ==
-->