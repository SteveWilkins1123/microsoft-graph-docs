---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

var graphClient = new GraphServiceClient(requestAdapter);

await graphClient.Me.Activities["{userActivity-id}"].HistoryItems["{activityHistoryItem-id}"].PutAsync();


```