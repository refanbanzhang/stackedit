## 分析Modal组件的html组成
**maskStyle**
遮罩样式
给ant-modal-mask添加css属性

**bodyStyle**
Modal body
给ant-modal-body添加css属性

**style**
可用于设置浮层的样式，调整浮层位置等
给ant-modal添加css属性

**wrapClassName**
对话框外层容器的类名
给ant-modal-wrap添加class类名

**width**
宽度




目前看来控制这个元素的className能够实现全屏切换
wrapClassName={isFullScreen ? 'fullscreen' : ''}









## 两者的差异是什么？
为什么在对antd Modal组件进行二次封装时，第一种不奏效？
```tsx
type ModalProps = React.ComponentProps<typeof Modal>
const ModalEnhanced: FC = (props: ModalProps) => {};
```
会报如下错误
Type '{ children: Element; title: string; visible: boolean; onOk: () => void; onCancel: () => void; }' is not assignable to type 'IntrinsicAttributes & { children?: ReactNode; }'.  
Property 'title' does not exist on type 'IntrinsicAttributes & { children?: ReactNode; }'.ts(2322)

工作良好
```
type ModalProps = React.ComponentProps<typeof Modal>
const ModalEnhanced: FC<ModalProps> = (props) => {};
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbMzkyMzMzMzAzLC0xMzE1NTk1NDU0LC0yND
A3NjU2MjgsLTQ3ODI5MDc3MCwxODg4OTYyMjY4LDgwMzkwMzA5
MCwxOTY2ODM1OTg1LC0zMTkyNjQyMjcsMTk5NTY1NDM1MSwtMT
c3NTQ3NjgzOV19
-->