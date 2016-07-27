## 物流系统集成方案

### 概述
为了实现固废管理系统固废外运车卡状态和汽车过磅数据管理，实现固废全生命周周的管理监控，通过 Web 服务接口配合 PI 实现与物流系统的对接。

### 集成流程

![LMS 集成](../images/lms-business.png)

#### 固废外运车卡信息同步（激活、更新、注销）
联系外运确定运输信息后，HSE 管理人员通过固废管理系统触发车卡激活或注销功能，固废管理系统通过 PI 主动向物流系统发起具体外运处置单的车卡信息同步请求，物流系统应该按照请求参数创建或更新（按照固废类型和业务单号查找）固废系统同步的运输信息，并标识固废特有的类型，根据车卡状态激活或注销相关联的车卡，实现固废车辆入场过磅时的身份验证。

#### 固废外运车辆过磅数据同步
固废车辆重车过磅结束后，物流管理系统通过 PI 向固废管理系统（EAD平台）发起过磅数据同步请求。固废系统根据物流系统发送的数据更新相关联的外运处置单过磅数据和状态，完成外运过磅业务环节。

### 异常影响
固废管理系统主动发起的固废外运车卡信息同步接口在物流系统异常时可以通过系统界面重新发起同步请求，短期内无法恢复的人工通知物流系统手工录入固废外运运输信息。物流系统异常造成无法同步过磅数据时，固废管理系统可以通过用户界面手工录入影响业务流转的关键数据。物流系统异常不会造成固废管理系统非过磅数据同步之外的其它业务正常运行。

固废管理系统异常时，会造成车辆过磅数据无法及时同步，记录数据同步异常状态，待固废管理系统恢复正常后，可以通过系统界面手工触发完成异常的过磅数据同步，也可以人工通知固废管理系统手工录入出现异常的过磅数据。固废管理系统异常不会影响物流管理系统的正常运行。



