
## 工时评估

### 权限
初始工作量：15
复用工作量：3

###

### 穿透
2

### 列表+详情
3

### 增删改查
2


## 分析Modal组件的html组成
**maskStyle**
遮罩样式
给ant-modal-mask添加css属性

**wrapClassName**
对话框外层容器的类名
给ant-modal-wrap添加class类名

**style**
可用于设置浮层的样式，调整浮层位置等
给ant-modal添加css属性

**width**
宽度
给ant-modal设置添加width属性

**bodyStyle**
Modal body
给ant-modal-body添加css属性

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
eyJoaXN0b3J5IjpbNTA3MjIwMjAyLC02Nzg5OTg2MDEsLTE1ND
M5Mjc5MSwtMTMxNTU5NTQ1NCwtMjQwNzY1NjI4LC00NzgyOTA3
NzAsMTg4ODk2MjI2OCw4MDM5MDMwOTAsMTk2NjgzNTk4NSwtMz
E5MjY0MjI3LDE5OTU2NTQzNTEsLTE3NzU0NzY4MzldfQ==
-->