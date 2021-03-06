# 创建负载均衡-CreateULB

创建负载均衡实例，可以选择内网或者外网

!> OuterMode 与 InnerMode 同时传 Yes 时，以 OuterMode 为准
当传了 InnerMode: Yes 之后，需要传一个 SubnetId 来表示用户选择了哪个子网

# Request Parameters
|Parameter name|Type|Description|Required|
|---|---|---|---|
|Region|string|地域。 参见 [地域和可用区列表](api/summary/regionlist)|**Yes**|
|ProjectId|string|项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](api/summary/get_project_list)|No|
|ULBName|string|负载均衡的名字，默认值为“ULB”|No|
|Tag|string|业务组|No|
|Remark|string|备注|No|
|OuterMode|string|创建的ULB是否为外网模式，默认即为外网模式|No|
|InnerMode|string|创建的ULB是否为内网模式|No|
|ChargeType|string|付费方式, 枚举值为: Year, 按年付费; Month, 按月付费; Dynamic, 按时付费|No|
|VPCId|string|ULB所在的VPC的ID, 如果不传则使用默认的VPC|No|
|SubnetId|string|内网ULB 所属的子网ID，如果不传则使用默认的子网|No|
|BusinessId|string|ULB 所属的业务组ID，如果不传则使用默认的业务组|No|
|FirewallId|string|防火墙ID，如果不传，则默认不绑定防火墙|No|

# Response Elements
|Parameter name|Type|Description|Required|
|---|---|---|---|
|RetCode|int|返回码|**Yes**|
|Action|string|操作名称|**Yes**|
|ULBId|string|负载均衡实例的Id|No|
|IPv6AddressId|string|IPv6地址Id|No|

# Request Example
```
https://api.ucloud.cn/?Action=CreateULB
&Region=cn-bj2
&ProjectId=project-XXXXX
&ULBName=test
&OuterMode=Yes
&ChargeType=Month
&VPCId=vnet-XXXXX
&SubnetId=subnet-XXXXX
&Tag=test
&FirewallId=wXfLAbgy
```

# Response Example
```
{
    "Action": "CreateULBResponse", 
    "ULBId": "ulb-XXXXX", 
    "IPv6AddressId": "LTPlnlOm", 
    "RetCode": 0
}
```

