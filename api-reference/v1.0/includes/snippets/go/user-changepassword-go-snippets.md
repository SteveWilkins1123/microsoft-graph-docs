---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphusers "github.com/microsoftgraph/msgraph-sdk-go/users"
	  //other-imports
)

graphClient, err := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphusers.NewChangePasswordPostRequestBody()
currentPassword := "xWwvJ]6NMw+bWH-d"
requestBody.SetCurrentPassword(&currentPassword) 
newPassword := "0eM85N54wFxWwvJ]"
requestBody.SetNewPassword(&newPassword) 

graphClient.Me().ChangePassword().Post(context.Background(), requestBody, nil)


```