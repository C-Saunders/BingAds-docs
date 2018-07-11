---
title: "KeywordBidding object"
description: "Contains the methods for specifying the keyword's bid values."
author: "brapel"
manager: ehansen

ms.author: "v-brapel"
ms.service: "bingads-scripts"
ms.topic: "article"
---

# KeywordBidding

Contains the methods for specifying the keyword's bid values.

## Methods

|Method Name|Return Type|Description|
|-|-|-
[clearCpc](#clearcpc)|void|Removes the keyword's CPC bid.
[getCpc](#getcpc)|double|Returns the keyword's CPC bid.
[setCpc(double cpc)](#setcpc~double-cpc~)|void|Sets the maximum CPC bid for the keyword.

## <a name="clearcpc"></a>clearCpc
Removes the keyword's CPC bid. 

### Returns

|Type|Description|
|-|-
void|Returns nothing.

## <a name="getcpc"></a>getCpc
Returns the keyword's CPC bid. 

### Returns

|Type|Description|
|-|-
double|The keyword's CPC bid. If the keyword doesn't specify a bid, this field contains the bid inherited from the ad group.

## <a name="setcpc~double-cpc~"></a>setCpc(double cpc)
Sets the CPC bid for the keyword. 

Specifies the bid amount to use when the keyword matches the user's search term and the ad group's bid strategy is ManualCpc or EnhancedCpc.

To use the bid amount specified at the ad group level, call the `clearCpc()` method.

For more information about bid amounts, see [Bid](/bingads/campaign-management-service/keyword#bid) and [BiddingScheme](/bingads/campaign-management-service/keyword#biddingscheme). 

If you specify a property value that's not valid, the call silently fails. To confirm whether the property was actually updated, you must get the object again and test whether the property's value equals the new value. For information, see [Handling errors and warnings](../concepts/errors-and-warnings.md).

### Arguments

|Name|Type|Description|
|-|-|-
cpc|double|The CPC bid for the keyword. The account's currency determines the minimum and maximum bid values. For more information, see [Bid and budget currencies](/bingads/guides/currencies#bidandbudget).

### Returns

|Type|Description|
|-|-
void|Returns nothing.



## See also

[Keyword.bidding()](Keyword.md#bidding)