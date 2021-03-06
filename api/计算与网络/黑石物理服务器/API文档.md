

黑石物理服务器(Cloud Physical Machine)是种可以按需购买、按量付费的物理服务器租赁服务，提供给您云端专用的高性能、安全隔离的物理集群。使用该服务，您只需确定机型和数量，获取服务器时间将被缩短至4小时，服务器供应、运维工作交由腾讯云，您可专心于业务创新。

本文档主要介绍如何调用黑石物理服务器 API， 并给出调用示例。您可通过API创建、销毁、重启黑石物理服务器等，所有API列表请对参考。[API概览页](/doc/api/456/6632)。

请确保在使用这些接口前，已充分了解了[黑石物理服务器](/doc/product/213/495)。


## 1. 术语表


| 术语 | 全称  | 中文 | 说明 |
|---------|---------|---------|---------|
| Instance | Instance |实例 | 指代一台黑石物理服务器。
| Zone | Zone | 可用区| 指腾讯云在同一地域内电力和网络互相独立的物理数据中心。目标是能够保证可用区之间故障相互隔离，不出现故障扩散，使得用户的业务持续在线服务。 |
|无 | 无 | 包年包月 |	一种计费模式，参看[计费模式说明](https://cloud.tencent.com/doc/product/213/2180#1.-.E5.8C.85.E5.B9.B4.E5.8C.85.E6.9C.88)。|


#### 输入参数与返回参数释义
* limit 和 offset

	>用于控制分页的参数；当结果数量超过了 limit 时，返回的结果数与limit一致。通过 limit 和 offset 两个参数可控制分页：limit 为单次返回的最多条目数量，offset 为偏移量。
	>举例来说，参数 offset=0&limit=20 返回第0到20项，offset=20&limit=20 返回第20到40项，offset=40&limit=20 返回第40到60项；以此类推。
	
* id.n

	>同时输入多个参数的格式。当遇到形如这样的格式时，那么该输入参数可以同时传多个。例如：
	
	> id.0=10.12.243.21&id.1=10.11.243.21&id.2=10.12.243.21&id.3=10.13.243.21...
	
	> 以此类推（以下标0开始）。


## 2. API快速入门  

通过几个典型的场景，举例如何使用CAM API：

1. 调用[BuyDevice](/doc/api/456/6638), 传入zoneId，deviceClassCode等参数，即可购买一台黑石物理服务器
2. 调用[EipBmApply](/doc/api/456/6669),传入goodsNum，payMode等参数，即可申请与goodsNum数量相符的eip
3. 调用[EipBmBindRs](/doc/api/456/6673)，传入eipId，instanceId等参数，即可以将指定的EIP绑定到指定的服务器上

## 3. 使用限制 
* CPM API 调用配额为：1000次/分钟；且单一API不超过100次/分钟。
* 更多限制描述，请参考其他API接口文档或是产品文档。



