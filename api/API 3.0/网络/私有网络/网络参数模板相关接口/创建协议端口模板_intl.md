## 1. API Description

Domain name for API request: vpc.tencentcloudapi.com.

This API (CreateServiceTemplate) is used to create a protocol port template.

A maximum of 100 requests can be initiated per second for this API.

Note: This API supports Finance regions. Since Finance regions and non-Finance regions are isolated and not interconnected. If the common parameter Region is a Finance region (such as ap-shanghai-fsi), you need to specify a domain name containing the Finance region that should be identical to the value of Region field, for example: vpc.ap-shanghai-fsi.tencentcloudapi.com.



## 2. Input Parameters

The following request parameter list only provides API request parameters and some common parameters. For the complete common parameter list, see [Common Request Parameters](/document/api/215/15692).

| Parameter Name | Required | Type | Description |
|---------|---------|---------|---------|
| Action | Yes | String | Common parameter. The value used for this API: CreateServiceTemplate |
| Version | Yes |  String | Common parameter. The value used for this API: 2017-03-12 |
| Region | Yes |  String | Common parameter. For more information, please see the [list of regions](/document/api/215/15692#.E5.9C.B0.E5.9F.9F.E5.88.97.E8.A1.A8) supported by the product. |
| ServiceTemplateName | Yes | String | Protocol port template name |
| Services.N | Yes | Array of String | Supports single port, multiple ports, consecutive ports and all ports. Supported protocols include TCP, UDP, ICMP, and GRE. |

## 3. Output Parameters

| Parameter Name | Type | Description |
|---------|---------|---------|
| ServiceTemplate | [ServiceTemplate](/document/api/215/##ServiceTemplate) | Protocol port template object. |
| RequestId | String | The unique request ID, which is returned for each request. RequestId is required for locating a problem. |

## 4. Error Codes

The following only lists the error codes related to the API business logic. For other error codes, see [Common Error Codes](/document/api/215/15694#.E5.85.AC.E5.85.B1.E9.94.99.E8.AF.AF.E7.A0.81).

| Error Code | Description |
|---------|---------|
| InvalidParameterValue | Invalid parameter value. |

## 5. Example

### Example 1 Create a protocol port template

#### Input example

```
https://vpc.tencentcloudapi.com/?Action=CreateServiceTemplate
&Version=2017-03-12
&ServiceTemplateName=TestName
&Services.0=TCP:8080
&Services.1=UDP:99
&<Common request parameters>
```

#### Output example

```
{
  "Response": {
    "RequestId": "20569756-56ba-4a13-b545-e1528d5cb239",
    "ServiceTemplate": {
      "CreatedTime": "2018-04-03 21:19:31",
      "ServiceSet": [
        "tcp: 8080",
        "udp: 99"
      ],
      "ServiceTemplateId": "ppm-bu8cir16",
      "ServiceTemplateName": "TestName"
    }
  }
}
```


## 6. Other Resources

Cloud API 3.0 comes with the following development tools to make it easier to call the API.

* [Tencent Cloud SDK 3.0 for Python](https://github.com/TencentCloud/tencentcloud-sdk-python)
* [Tencent Cloud SDK 3.0 for Java](https://github.com/TencentCloud/tencentcloud-sdk-java)
* [Tencent Cloud SDK 3.0 for PHP](https://github.com/TencentCloud/tencentcloud-sdk-php)
* [Tencent Cloud SDK 3.0 for Go](https://github.com/TencentCloud/tencentcloud-sdk-go)
* [Tencent Cloud SDK 3.0 for NodeJS](https://github.com/TencentCloud/tencentcloud-sdk-nodejs)
* [Tencent Cloud SDK 3.0 for .NET](https://github.com/TencentCloud/tencentcloud-sdk-dotnet)
* [Tencent Cloud CLI 3.0](https://cloud.tencent.com/document/product/440/6176)

