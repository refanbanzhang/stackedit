
## 工时评估

### 权限
初始工作量：15
复用工作量：2

### 流程审批
初始工作量：15
复用工作量：2

### 穿透
2

### 列表
2

### 详情
2

### 增删改查（自带详情）
2

### 导入
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
## 分析下钻实现逻辑
1. 点击核算部门按钮
2. 调用getHsbmIdData
	获取表单参数
	发起getLrhsListPage请求
	

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTUxOTg3MjE3NSwtNDM1NDkxNDYwLDM0Nj
cyMjE1NSwxNjA0MjA4NzUzLC0xOTk3MDAwNjIzLC02Nzg5OTg2
MDEsLTE1NDM5Mjc5MSwtMTMxNTU5NTQ1NCwtMjQwNzY1NjI4LC
00NzgyOTA3NzAsMTg4ODk2MjI2OCw4MDM5MDMwOTAsMTk2Njgz
NTk4NSwtMzE5MjY0MjI3LDE5OTU2NTQzNTEsLTE3NzU0NzY4Mz
ldfQ==
-->