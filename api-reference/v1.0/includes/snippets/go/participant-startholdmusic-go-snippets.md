---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphcommunications "github.com/microsoftgraph/msgraph-sdk-go/communications"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  //other-imports
)

graphClient, err := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphcommunications.NewStartHoldMusicPostRequestBody()
customPrompt := graphmodels.NewPrompt()
additionalData := map[string]interface{}{
mediaInfo := graphmodels.New()
uri := "https://bot.contoso.com/onHold.wav"
mediaInfo.SetUri(&uri) 
	customPrompt.SetMediaInfo(mediaInfo)
}
customPrompt.SetAdditionalData(additionalData)
requestBody.SetCustomPrompt(customPrompt)
clientContext := "d45324c1-fcb5-430a-902c-f20af696537c"
requestBody.SetClientContext(&clientContext) 

result, err := graphClient.Communications().Calls().ByCallId("call-id").Participants().ByParticipantId("participant-id").StartHoldMusic().Post(context.Background(), requestBody, nil)


```