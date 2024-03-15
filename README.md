## 分析Modal组件的html组成
maskStyle 遮罩样式
bodyStyle Modal body
style 可用于设置浮层的样式，调整浮层位置等
wrapClassName 对话框外层容器的类名
width 宽度


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
eyJoaXN0b3J5IjpbLTEzMTU1OTU0NTQsLTI0MDc2NTYyOCwtND
c4MjkwNzcwLDE4ODg5NjIyNjgsODAzOTAzMDkwLDE5NjY4MzU5
ODUsLTMxOTI2NDIyNywxOTk1NjU0MzUxLC0xNzc1NDc2ODM5XX
0=
-->