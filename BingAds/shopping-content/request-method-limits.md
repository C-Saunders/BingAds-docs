---
title: "Request and method limits"
description: "Provides limits for HTTP requests and batch method calls"
author: "swhite-msft"
manager: "ehansen"

ms.service: "shopping-content-api"
ms.topic: "article"
ms.author: "scottwhi"
---

# Request and method call limits

The following are the recommended limits that you should follow when implementing your Content API solution. These limits are currently not enforced but because they may be enforced in the future, you should implement them now.

### How many queries can I send per second? 

You should limit the number of HTTP requests you send per second to 40. 

### How many methods can I call per minute and per day?

You should limit the number of method calls you make per minute to 60,000 and the number of calls you make per day to 20,000,000.
 
Every method call is an HTTP request except for batch requests, which may contain up to 300 method calls. 

If you send only single-method requests, you probably won't exceed the per minute or per day limits. But if you need to update multiple offers, sending single-method requests isn't recommended. Instead, you should use batch requests.

If you maximize batch requests, you'll probably exceed the per minute and per day limits. For example, 40 QPS * 60 seconds * 300 methods = 720,000 methods per minute.

If you want to maximize QPS, you need to limit the number of batch methods to 25. And if you want to maximize batch methods, you need to limit QPS to three.

### How do batch requests count against the limits?

Using [batch requests](manage-products.md#-using-batch-processing) to process multiple product offers does reduce the number of requests that count against the QPS limit. For example, if you update 10 offers using a batch request, it counts as one request against the QPS limit instead of 10 if you sent 10 separate requests.

But, using batch requests doesn't help you reduce the number of method calls. Each item in the batch request counts as one method call. For example, a batch request with 100 items counts as 100 method calls against the method calls limit.  


### Do dry-run requests count against the limits?

Although using the [dry-run](products-resource.md#dryrun) query parameter lets you test your code without affecting your offers, the requests and method calls count against the QPS and method call limits. 


## blah

|Limit|Description
|-|-
|Queries per second (QPS)|Limit the number of HTTP requests you send per second to 40.
|Method calls per minute|Limit the number of method calls you make per minute to 60,000.
|Method calls per day|Limit the number of method calls you make per day to 20,000,000.

Every method call is an HTTP request except for batch requests, which may contain up to 300 method calls. 

### How do batch requests count against the limits?

Using [batch requests](manage-products.md#-using-batch-processing) to process multiple product offers does reduce the number of requests that count against the QPS limit. For example, if you update 10 offers using a batch request, it counts as one request against the QPS limit instead of 10 if you sent 10 separate requests.

But, using batch requests doesn't help you reduce the number of method calls. Each item in the batch request counts as one method call. For example, a batch request with 100 items counts as 100 method calls against the method calls limit.  


### Do dry-run requests count against the limits?

Although using the [dry-run](products-resource.md#dryrun) query parameter lets you test your code without affecting your offers, the requests and method calls count against the QPS and method call limits. 

### Can I maximize batch requests?

A batch request may contain up to 300 method calls. If you maximize batch requests, you'll probably exceed the per minute and per day limits. For example, 40 QPS * 60 seconds * 300 methods = 720,000 methods per minute.

If you want to maximize QPS, you need to limit the number of batch methods to 25. And if you want to maximize batch methods, you need to limit QPS to three.
