---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphusers "github.com/microsoftgraph/msgraph-beta-sdk-go/users"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/models"
	  //other-imports
)

graphClient, err := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphusers.NewTentativelyAcceptPostRequestBody()
comment := "I may not be able to make this week. How about next week?"
requestBody.SetComment(&comment) 
sendResponse := true
requestBody.SetSendResponse(&sendResponse) 
proposedNewTime := graphmodels.NewTimeSlot()
start := graphmodels.NewDateTimeTimeZone()
dateTime := "2019-12-02T18:00:00"
start.SetDateTime(&dateTime) 
timeZone := "Pacific Standard Time"
start.SetTimeZone(&timeZone) 
proposedNewTime.SetStart(start)
end := graphmodels.NewDateTimeTimeZone()
dateTime := "2019-12-02T19:00:00"
end.SetDateTime(&dateTime) 
timeZone := "Pacific Standard Time"
end.SetTimeZone(&timeZone) 
proposedNewTime.SetEnd(end)
requestBody.SetProposedNewTime(proposedNewTime)

graphClient.Me().Events().ByEventId("event-id").TentativelyAccept().Post(context.Background(), requestBody, nil)


```