---
title: SearchAccounts Service Operation - Customer Management
ms.service: bing-ads-customer-management-service
ms.topic: article
author: Matt-UX
ms.author: matrob
description: Searches for accounts that match the request criteria.
dev_langs: 
  - csharp
  - java
  - php
  - python
---
# SearchAccounts Service Operation - Customer Management
Searches for accounts that match the request criteria. 

For example you can search for accounts that the current authenticated user can access.

> [!TIP]
> Please see the [Account Hierchy and User Permissions](../guides/account-hierarchy-permissions.md) guide for an overview with examples. 

## <a name="request"></a>Request Elements
The *SearchAccountsRequest* object defines the [body](#request-body) and [header](#request-header) elements of the service operation request. The elements must be in the same order as shown in the [Request SOAP](#request-soap). 

> [!NOTE]
> Unless otherwise noted below, all request elements are required.

### <a name="request-body"></a>Request Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="ordering"></a>Ordering|Determines the order of results by the specified property of an account.<br/><br/>This request element is optional. You can specify up to one [OrderBy](orderby.md) element in the array. Additional elements are not supported and will be ignored by the service.<br/><br/>If you set the [Field](orderby.md#field) element of the [OrderBy](orderby.md) object to "Id", "Name", or "Number", the returned [Accounts](#accounts) will be ordered by the account identifiers, names, or numbers accordingly.<br/><br/>This request element is optional.|[OrderBy](orderby.md) array|
|<a name="pageinfo"></a>PageInfo|Determines the index and size of results per page.|[Paging](paging.md)|
|<a name="predicates"></a>Predicates|Determines the conditions that all must be met to return accounts.<br/><br/>You must include exactly one predicate. If the predicate [Field](predicate.md#field) is set to "AccountLifeCycleStatus", then you must specify one additional predicate with the [Field](predicate.md#field) set to another value such as UserId.<br/><br/>For details about each supported predicate [Field](predicate.md#field) value see [Predicate Remarks](predicate.md#remarks).|[Predicate](predicate.md) array|

### <a name="request-header"></a>Request Header Elements
[!INCLUDE[request-header](./includes/request-header.md)]

## <a name="response"></a>Response Elements
The *SearchAccountsResponse* object defines the [body](#response-body) and [header](#response-header) elements of the service operation response. The elements are returned in the same order as shown in the [Response SOAP](#response-soap).

### <a name="response-body"></a>Response Body Elements

|Element|Description|Data Type|
|-----------|---------------|-------------|
|<a name="accounts"></a>Accounts|A list of accounts that meet the request criteria.|[AdvertiserAccount](advertiseraccount.md) array|

### <a name="response-header"></a>Response Header Elements
[!INCLUDE[response-header](./includes/response-header.md)]

## <a name="request-soap"></a>Request SOAP
This template was generated by a tool to show the [order](../guides/services-protocol.md#element-order) of the [body](#request-body) and [header](#request-header) elements for the SOAP request. For supported types that you can use with this service operation, see the [Request Body Elements](#request-body) reference above.

```xml
<s:Envelope xmlns:i="http://www.w3.org/2001/XMLSchema-instance" xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v13">
    <Action mustUnderstand="1">SearchAccounts</Action>
    <AuthenticationToken i:nil="false">ValueHere</AuthenticationToken>
    <DeveloperToken i:nil="false">ValueHere</DeveloperToken>
  </s:Header>
  <s:Body>
    <SearchAccountsRequest xmlns="https://bingads.microsoft.com/Customer/v13">
      <Predicates xmlns:e169="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e169:Predicate>
          <e169:Field i:nil="false">ValueHere</e169:Field>
          <e169:Operator>ValueHere</e169:Operator>
          <e169:Value i:nil="false">ValueHere</e169:Value>
        </e169:Predicate>
      </Predicates>
      <Ordering xmlns:e170="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e170:OrderBy>
          <e170:Field>ValueHere</e170:Field>
          <e170:Order>ValueHere</e170:Order>
        </e170:OrderBy>
      </Ordering>
      <PageInfo xmlns:e171="https://bingads.microsoft.com/Customer/v13/Entities" i:nil="false">
        <e171:Index>ValueHere</e171:Index>
        <e171:Size>ValueHere</e171:Size>
      </PageInfo>
    </SearchAccountsRequest>
  </s:Body>
</s:Envelope>
```

## <a name="response-soap"></a>Response SOAP
This template was generated by a tool to show the order of the [body](#response-body) and [header](#response-header) elements for the SOAP response.

```xml
<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">
  <s:Header xmlns="https://bingads.microsoft.com/Customer/v13">
    <TrackingId d3p1:nil="false" xmlns:d3p1="http://www.w3.org/2001/XMLSchema-instance">ValueHere</TrackingId>
  </s:Header>
  <s:Body>
    <SearchAccountsResponse xmlns="https://bingads.microsoft.com/Customer/v13">
      <Accounts xmlns:e172="https://bingads.microsoft.com/Customer/v13/Entities" d4p1:nil="false" xmlns:d4p1="http://www.w3.org/2001/XMLSchema-instance">
        <e172:AdvertiserAccount>
          <e172:BillToCustomerId d4p1:nil="false">ValueHere</e172:BillToCustomerId>
          <e172:CurrencyCode d4p1:nil="false">ValueHere</e172:CurrencyCode>
          <e172:AccountFinancialStatus d4p1:nil="false">ValueHere</e172:AccountFinancialStatus>
          <e172:Id d4p1:nil="false">ValueHere</e172:Id>
          <e172:Language d4p1:nil="false">ValueHere</e172:Language>
          <e172:LastModifiedByUserId d4p1:nil="false">ValueHere</e172:LastModifiedByUserId>
          <e172:LastModifiedTime d4p1:nil="false">ValueHere</e172:LastModifiedTime>
          <e172:Name d4p1:nil="false">ValueHere</e172:Name>
          <e172:Number d4p1:nil="false">ValueHere</e172:Number>
          <e172:ParentCustomerId>ValueHere</e172:ParentCustomerId>
          <e172:PaymentMethodId d4p1:nil="false">ValueHere</e172:PaymentMethodId>
          <e172:PaymentMethodType d4p1:nil="false">ValueHere</e172:PaymentMethodType>
          <e172:PrimaryUserId d4p1:nil="false">ValueHere</e172:PrimaryUserId>
          <e172:AccountLifeCycleStatus d4p1:nil="false">ValueHere</e172:AccountLifeCycleStatus>
          <e172:TimeStamp d4p1:nil="false">ValueHere</e172:TimeStamp>
          <e172:TimeZone d4p1:nil="false">ValueHere</e172:TimeZone>
          <e172:PauseReason d4p1:nil="false">ValueHere</e172:PauseReason>
          <e172:ForwardCompatibilityMap xmlns:e173="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e173:KeyValuePairOfstringstring>
              <e173:key d4p1:nil="false">ValueHere</e173:key>
              <e173:value d4p1:nil="false">ValueHere</e173:value>
            </e173:KeyValuePairOfstringstring>
          </e172:ForwardCompatibilityMap>
          <e172:LinkedAgencies d4p1:nil="false">
            <e172:CustomerInfo>
              <e172:Id d4p1:nil="false">ValueHere</e172:Id>
              <e172:Name d4p1:nil="false">ValueHere</e172:Name>
            </e172:CustomerInfo>
          </e172:LinkedAgencies>
          <e172:SalesHouseCustomerId d4p1:nil="false">ValueHere</e172:SalesHouseCustomerId>
          <e172:TaxInformation xmlns:e174="http://schemas.datacontract.org/2004/07/System.Collections.Generic" d4p1:nil="false">
            <e174:KeyValuePairOfstringstring>
              <e174:key d4p1:nil="false">ValueHere</e174:key>
              <e174:value d4p1:nil="false">ValueHere</e174:value>
            </e174:KeyValuePairOfstringstring>
          </e172:TaxInformation>
          <e172:BackUpPaymentInstrumentId d4p1:nil="false">ValueHere</e172:BackUpPaymentInstrumentId>
          <e172:BillingThresholdAmount d4p1:nil="false">ValueHere</e172:BillingThresholdAmount>
          <e172:BusinessAddress d4p1:nil="false">
            <e172:City d4p1:nil="false">ValueHere</e172:City>
            <e172:CountryCode d4p1:nil="false">ValueHere</e172:CountryCode>
            <e172:Id d4p1:nil="false">ValueHere</e172:Id>
            <e172:Line1 d4p1:nil="false">ValueHere</e172:Line1>
            <e172:Line2 d4p1:nil="false">ValueHere</e172:Line2>
            <e172:Line3 d4p1:nil="false">ValueHere</e172:Line3>
            <e172:Line4 d4p1:nil="false">ValueHere</e172:Line4>
            <e172:PostalCode d4p1:nil="false">ValueHere</e172:PostalCode>
            <e172:StateOrProvince d4p1:nil="false">ValueHere</e172:StateOrProvince>
            <e172:TimeStamp d4p1:nil="false">ValueHere</e172:TimeStamp>
            <e172:BusinessName d4p1:nil="false">ValueHere</e172:BusinessName>
          </e172:BusinessAddress>
          <e172:AutoTagType d4p1:nil="false">ValueHere</e172:AutoTagType>
          <e172:SoldToPaymentInstrumentId d4p1:nil="false">ValueHere</e172:SoldToPaymentInstrumentId>
        </e172:AdvertiserAccount>
      </Accounts>
    </SearchAccountsResponse>
  </s:Body>
</s:Envelope>
```

## <a name="example"></a>Code Syntax
The example syntax can be used with [Bing Ads SDKs](../guides/client-libraries.md). See [Bing Ads API Code Examples](../guides/code-examples.md) for more examples.
```csharp
public async Task<SearchAccountsResponse> SearchAccountsAsync(
	IList<Predicate> predicates,
	IList<OrderBy> ordering,
	Paging pageInfo)
{
	var request = new SearchAccountsRequest
	{
		Predicates = predicates,
		Ordering = ordering,
		PageInfo = pageInfo
	};

	return (await CustomerManagementService.CallAsync((s, r) => s.SearchAccountsAsync(r), request));
}
```
```java
static SearchAccountsResponse searchAccounts(
	ArrayOfPredicate predicates,
	ArrayOfOrderBy ordering,
	Paging pageInfo) throws RemoteException, Exception
{
	SearchAccountsRequest request = new SearchAccountsRequest();

	request.setPredicates(predicates);
	request.setOrdering(ordering);
	request.setPageInfo(pageInfo);

	return CustomerManagementService.getService().searchAccounts(request);
}
```
```php
static function SearchAccounts(
	$predicates,
	$ordering,
	$pageInfo)
{

	$GLOBALS['Proxy'] = $GLOBALS['CustomerManagementProxy'];

	$request = new SearchAccountsRequest();

	$request->Predicates = $predicates;
	$request->Ordering = $ordering;
	$request->PageInfo = $pageInfo;

	return $GLOBALS['CustomerManagementProxy']->GetService()->SearchAccounts($request);
}
```
```python
response=customermanagement_service.SearchAccounts(
	Predicates=Predicates,
	Ordering=Ordering,
	PageInfo=PageInfo)
```

## Requirements
Service: [CustomerManagementService.svc v13](https://clientcenter.api.bingads.microsoft.com/Api/CustomerManagement/v13/CustomerManagementService.svc)  
Namespace: https\://bingads.microsoft.com/Customer/v13  

