# DescribeZones {#doc_api_NAS_DescribeZones .reference}

DescribeZones用于查询某个 Region 下的所有可用区及可用区所支持的 NAS 类型。

只发布中国站

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=NAS&api=DescribeZones&type=RPC&version=2017-06-26)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|RegionId|String|是|cn-hangzhou|地域 ID

 |
|Action|String|否|DescribeZones|操作接口名，系统规定参数，取值：DescribeZones

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|A70BEE5D-76D3-49FB-B58F-1F398211A5C3|请求 ID

 |
|Zones| | |每个元素是一个 Zone

 |
|Capacity| |1|容量型存储

 |
|Performance| |0|性能型存储

 |
|ZoneId|String|cn-hangzhou-b|可用区ID

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://nas.cn-hangzhou.aliyuncs.com/?Action=DescribeZones
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeZones>
      <RequestId>A70BEE5D-76D3-49FB-B58F-1F398211A5C3</RequestId>
      <Zones>
            <Zone>
                  <Performance>
            </Performance>
                  <Capacity>
                        <Protocol>nfs</Protocol>
                        <Protocol>smb</Protocol>
                        <Protocol>nasplus</Protocol>
                  </Capacity>
                  <ZoneId>cn-hangzhou-b</ZoneId>
            </Zone>
            <Zone>
                  <Performance>
                        <Protocol>nfs</Protocol>
                        <Protocol>smb</Protocol>
                  </Performance>
                  <Capacity>
                        <Protocol>nfs</Protocol>
                        <Protocol>smb</Protocol>
                        <Protocol>nasplus</Protocol>
                  </Capacity>
                  <ZoneId>cn-hangzhou-g</ZoneId>
            </Zone>
            <Zone>
                  <Performance>
                        <Protocol>nfs</Protocol>
                        <Protocol>smb</Protocol>
                        <Protocol>newnfs</Protocol>
                  </Performance>
                  <Capacity>
            </Capacity>
                  <ZoneId>cn-hangzhou-f</ZoneId>
            </Zone>
      </Zones>
</DescribeZones>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"A70BEE5D-76D3-49FB-B58F-1F398211A5C3",
	"Zones":{
		"Zone":[
			{
				"ZoneId":"cn-hangzhou-b",
				"Capacity":{
					"Protocol":[
						"nfs",
						"smb",
						"nasplus"
					]
				},
				"Performance":{
					"Protocol":[]
				}
			},
			{
				"ZoneId":"cn-hangzhou-g",
				"Capacity":{
					"Protocol":[
						"nfs",
						"smb",
						"nasplus"
					]
				},
				"Performance":{
					"Protocol":[
						"nfs",
						"smb"
					]
				}
			},
			{
				"ZoneId":"cn-hangzhou-f",
				"Capacity":{
					"Protocol":[]
				},
				"Performance":{
					"Protocol":[
						"nfs",
						"smb",
						"newnfs"
					]
				}
			}
		]
	}
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|500|InternalError|The request processing has failed due to some unknown error.|给您带来的不便，深感抱歉，请稍后再试。|
|404|InvalidRegionId.NotFound|The specified Region is not found.|请求的 Region 不存在或暂未提供服务。|

访问[错误中心](https://error-center.aliyun.com/status/product/NAS)查看更多错误码。

