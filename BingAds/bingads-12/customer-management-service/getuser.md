---
title: GetUser Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Gets the details of a user.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# GetUser Service Operation - Customer Management
Gets the details of a user.

## <a name="request"></a>Request Elements
The *GetUserRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

### <a name="request-body"></a>Request Body Elements


|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="includelinkedaccountids"></a>IncludeLinkedAccountIds|Determines a) whether or not the [CustomerRole](customerrole.md) objects that represent the user's permissions on agency-linked accounts should be returned, and b) whether or not the [LinkedAccountIds](customerrole.md#linkedaccountids) element should be included in all returned [CustomerRole](customerrole.md) objects.<br /><br />If this flag is set to *True*, a) the [CustomerRole](customerrole.md) objects that represent the user's permissions for agency-linked accounts will be returned, and b) the [LinkedAccountIds](customerrole.md#linkedaccountids) element will be included in all returned [CustomerRole](customerrole.md) objects.<br/><br/>Otherwise if the flag is *False*, null, or not provided, a) the [CustomerRole](customerrole.md) objects that represent the user's permissions for agency-linked accounts will not be returned, and b) the [LinkedAccountIds](customerrole.md#linkedaccountids) element will not be included in any returned [CustomerRole](customerrole.md) objects.|**boolean**|
|<a name="userid"></a>UserId|The identifier of the user to get.<br /><br /> If this element is null or not provided, the response will include details for the authenticated user specified in the request header.|**long**|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *GetUserResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|                  Element                  |                                                                                                                                                                                                                                                                                                                                                                                                                               Description                                                                                                                                                                                                                                                                                                                                                                                                                               |               Data Type               |
|-------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------|
| <a name="customerroles"></a>CustomerRoles | The list of roles that a user has for each customer or list of accounts.<br/><br/>At minimum one list item will be returned. If a user's credentials can access multiple customers, then one [CustomerRole](customerrole.md) object per customer will be returned.<br/><br/>You can view all of your own roles across all customers; however, you will only see the roles of other users as it pertains to customers that you can access. For example let's say you@contoso.com and another-user@contoso.com can access Customer A. The other user might also have access to Customer B and C; however when you call this operation with their user identifier, you will only see their role under Customer A. When another-user@contoso.com calls this operation with their own credentials, the operation would return three [CustomerRole](customerrole.md) objects. | [CustomerRole](customerrole.md) array |
|          <a name="user"></a>User          |                                                                                                                                                                                                                                                                                                                                                                                                         A user object that contains information about the user.                                                                                                                                                                                                                                                                                                                                                                                                         |            [User](user.md)            |

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-header) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <Action mustUnderstand="1">GetUser</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <GetUserRequest xmlns="https://bingads.microsoft.com/Customer/v12">
      <UserId i:nil="false">ValueHere</UserId>
      <IncludeLinkedAccountIds i:nil="false">ValueHere</IncludeLinkedAccountIds>
    </GetUserRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
This template was generated by a tool to show the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v12">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <GetUserResponse xmlns="https://bingads.microsoft.com/Customer/v12">
      <User xmlns:e17="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e17:ContactInfo d4p1:nil="false">
          <e17:Address d4p1:nil="false">
            <e17:City d4p1:nil="false">ValueHere</e17:City>
            <e17:CountryCode d4p1:nil="false">ValueHere</e17:CountryCode>
            <e17:Id d4p1:nil="false">ValueHere</e17:Id>
            <e17:Line1 d4p1:nil="false">ValueHere</e17:Line1>
            <e17:Line2 d4p1:nil="false">ValueHere</e17:Line2>
            <e17:Line3 d4p1:nil="false">ValueHere</e17:Line3>
            <e17:Line4 d4p1:nil="false">ValueHere</e17:Line4>
            <e17:PostalCode d4p1:nil="false">ValueHere</e17:PostalCode>
            <e17:StateOrProvince d4p1:nil="false">ValueHere</e17:StateOrProvince>
            <e17:TimeStamp d4p1:nil="false">ValueHere</e17:TimeStamp>
            <e17:BusinessName d4p1:nil="false">ValueHere</e17:BusinessName>
          </e17:Address>
          <e17:ContactByPhone d4p1:nil="false">ValueHere</e17:ContactByPhone>
          <e17:ContactByPostalMail d4p1:nil="false">ValueHere</e17:ContactByPostalMail>
          <e17:Email d4p1:nil="false">ValueHere</e17:Email>
          <e17:EmailFormat d4p1:nil="false">ValueHere</e17:EmailFormat>
          <e17:Fax d4p1:nil="false">ValueHere</e17:Fax>
          <e17:HomePhone d4p1:nil="false">ValueHere</e17:HomePhone>
          <e17:Id d4p1:nil="false">ValueHere</e17:Id>
          <e17:Mobile d4p1:nil="false">ValueHere</e17:Mobile>
          <e17:Phone1 d4p1:nil="false">ValueHere</e17:Phone1>
          <e17:Phone2 d4p1:nil="false">ValueHere</e17:Phone2>
        </e17:ContactInfo>
        <e17:CustomerId d4p1:nil="false">ValueHere</e17:CustomerId>
        <e17:Id d4p1:nil="false">ValueHere</e17:Id>
        <e17:JobTitle d4p1:nil="false">ValueHere</e17:JobTitle>
        <e17:LastModifiedByUserId d4p1:nil="false">ValueHere</e17:LastModifiedByUserId>
        <e17:LastModifiedTime d4p1:nil="false">ValueHere</e17:LastModifiedTime>
        <e17:Lcid d4p1:nil="false">ValueHere</e17:Lcid>
        <e17:Name d4p1:nil="false">
          <e17:FirstName d4p1:nil="false">ValueHere</e17:FirstName>
          <e17:LastName d4p1:nil="false">ValueHere</e17:LastName>
          <e17:MiddleInitial d4p1:nil="false">ValueHere</e17:MiddleInitial>
        </e17:Name>
        <e17:Password d4p1:nil="false">ValueHere</e17:Password>
        <e17:SecretAnswer d4p1:nil="false">ValueHere</e17:SecretAnswer>
        <e17:SecretQuestion>ValueHere</e17:SecretQuestion>
        <e17:UserLifeCycleStatus d4p1:nil="false">ValueHere</e17:UserLifeCycleStatus>
        <e17:TimeStamp d4p1:nil="false">ValueHere</e17:TimeStamp>
        <e17:UserName d4p1:nil="false">ValueHere</e17:UserName>
        <e17:ForwardCompatibilityMap xmlns:e18="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
          <e18:KeyValuePairOfstringstring>
            <e18:key d4p1:nil="false">ValueHere</e18:key>
            <e18:value d4p1:nil="false">ValueHere</e18:value>
          </e18:KeyValuePairOfstringstring>
        </e17:ForwardCompatibilityMap>
      </User>
      <CustomerRoles xmlns:e19="https://bingads.microsoft.com/Customer/v12/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e19:CustomerRole>
          <e19:RoleId>ValueHere</e19:RoleId>
          <e19:CustomerId>ValueHere</e19:CustomerId>
          <e19:AccountIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </e19:AccountIds>
          <e19:LinkedAccountIds d4p1:nil="false" xmlns:a1="http://schemas.microsoft.com/2003/10/Serialization/Arrays">
            <a1:long>ValueHere</a1:long>
          </e19:LinkedAccountIds>
        </e19:CustomerRole>
      </CustomerRoles>
    </GetUserResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<GetUserResponse> GetUserAsync(
    long? userId,
    bool? includeLinkedAccountIds)
{
    var request = new GetUserRequest
    {
        UserId = userId,
        IncludeLinkedAccountIds = includeLinkedAccountIds
    };

    return (await CustomerManagementService.CallAsync((s, r) => s.GetUserAsync(r), request));
}
```
```java
static GetUserResponse getUser(
    java.lang.Long userId,
    boolean includeLinkedAccountIds) throws RemoteException, Exception
{
    GetUserRequest request = new GetUserRequest();

    request.setUserId(userId);
    request.setIncludeLinkedAccountIds(includeLinkedAccountIds);

    return CustomerManagementService.getService().getUser(request);
}
```
```php
static function GetUser(
    $userId,
    $includeLinkedAccountIds)
{

    $GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

    $request = new GetUserRequest();

    $request->UserId = $userId;
    $request->IncludeLinkedAccountIds = $includeLinkedAccountIds;

    return $GLOBALS['CustomerManagementProxy']->GetService()->GetUser($request);
}
```
```python
response=customermanagement_service.GetUser(
    UserId=UserId,
    IncludeLinkedAccountIds=IncludeLinkedAccountIds)
```

## Requirements
Service: [CustomerManagementService.svc v12](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v12/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v12  

