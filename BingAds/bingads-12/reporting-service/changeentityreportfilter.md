---
title: ChangeEntityReportFilter Value Set - Reporting
ms.service: bing-ads-reporting-service
ms.topic: article
author: eric-urban
ms.author: eur
description: Defines the types of entities by which you can filter the report data.
---
> [!IMPORTANT]
> This Bing Ads API Version 12 preview documentation is subject to change. To return to version 11 content, use the version selector near the table of contents at the top and left side of the page.

# ChangeEntityReportFilter Value Set - Reporting
Defines the types of entities by which you can filter the report data.

## Syntax
```xml
<xs:simpleType name="ChangeEntityReportFilter" xmlns:xs="http://www.w3.org/2001/XMLSchema">
  <xs:list>
    <xs:simpleType>
      <xs:restriction base="xs:string">
        <xs:enumeration value="Account" />
        <xs:enumeration value="Campaign" />
        <xs:enumeration value="AdGroup" />
        <xs:enumeration value="Ad" />
        <xs:enumeration value="Keyword" />
      </xs:restriction>
    </xs:simpleType>
  </xs:list>
</xs:simpleType>
```

## <a name="values"></a>Values

|Value|Description|
|-----------|---------------|
|<a name="account"></a>Account|The report will include data for accounts that have been added or deleted, or that have had account elements updated.<br /><br /> The report will include all entity types not represented by other filter values, for example ad extensions.|
|<a name="ad"></a>Ad|The report will include data for ads that have been added or deleted, or that have had ad elements updated.|
|<a name="adgroup"></a>AdGroup|The report will include data for ad groups that have been added or deleted, or that have had ad group elements updated.|
|<a name="campaign"></a>Campaign|The report will include data for campaigns that have been added or deleted, or that have had campaign elements updated.|
|<a name="keyword"></a>Keyword|The report will include data for keywords that have been added or deleted, or that have had keyword elements updated.|

## Requirements
Service: [ReportingService.svc v12](https://reporting.api.bingads.microsoft.com/Api/Advertiser/Reporting/v11/ReportingService.svc)  
Namespace: https\://bingads.microsoft.com/Reporting/v12  

## Used By
[SearchCampaignChangeHistoryReportFilter](searchcampaignchangehistoryreportfilter.md)  