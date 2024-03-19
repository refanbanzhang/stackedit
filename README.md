
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
	
## oppo审核被拒


#### 了解问题
『APP、SDK未告知用户收集个人信息的目的、方式、范围且未经用户 同意，私自收集用户个人信息的行为』
app内有做到。

#### 分析问题（得到解决方案）
app未发现问题，找客服解决。

平台反馈原因：
app提前调用api。

解决方案：



#### 解决问题（执行方案）
提供分析结果给客服。

#### 验证问题

#### 总结问题

<!--stackedit_data:
eyJoaXN0b3J5IjpbMzc2NjM1MDE5LC0xNjQyMDkyNjk1LC0yMD
YxNTgxNTU3LDE5MTgwMDA3MDAsLTE5MzM4NzY0MTMsLTM1ODYx
NjUzNCwtNzY1NTA3ODE3LC0xMzYxMjQ4MjE3LDExODAxMzY3Mi
wtNTE5ODcyMTc1LC00MzU0OTE0NjAsMzQ2NzIyMTU1LDE2MDQy
MDg3NTMsLTE5OTcwMDA2MjMsLTY3ODk5ODYwMSwtMTU0MzkyNz
kxLC0xMzE1NTk1NDU0LC0yNDA3NjU2MjgsLTQ3ODI5MDc3MCwx
ODg4OTYyMjY4XX0=
-->