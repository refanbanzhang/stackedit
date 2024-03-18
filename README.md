
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
	把下钻级别的查询参数存储在level level1 level2中
3. 在goBack中取出level数据使用
	
## oppo审核被拒



![输入图片说明](/imgs/2024-03-18/DtGTcx1bvIolRARX.png)

>『APP、SDK未告知用户收集个人信息的目的、方式、范围且未经用户 同意，私自收集用户个人信息的行为』，我们的APP没有收集用户信息吧？

https://open.oppomobile.com/new/introduction?page_name=audit-open

建议参考《工业和信息化部关于开展纵深推进APP侵害用户权益专项整治行动的通知》工信部信管函〔2020〕164号进行整改，还可以通过开放平台隐私服务自测获取详细报告（https://open.oppomobile.com/new/introduction?page_name=audit-open）


### 解决问题的流程

#### 了解问题

#### 分析问题（罗列解决方案）
添加用户协议勾选
发布时告知审核平台使用了哪些获取用户信息的api

#### 开始解决（执行方案）

#### 验证问题

#### 总结

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc2NTUwNzgxNywtMTM2MTI0ODIxNywxMT
gwMTM2NzIsLTUxOTg3MjE3NSwtNDM1NDkxNDYwLDM0NjcyMjE1
NSwxNjA0MjA4NzUzLC0xOTk3MDAwNjIzLC02Nzg5OTg2MDEsLT
E1NDM5Mjc5MSwtMTMxNTU5NTQ1NCwtMjQwNzY1NjI4LC00Nzgy
OTA3NzAsMTg4ODk2MjI2OCw4MDM5MDMwOTAsMTk2NjgzNTk4NS
wtMzE5MjY0MjI3LDE5OTU2NTQzNTEsLTE3NzU0NzY4MzldfQ==

-->