---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphcommunications "github.com/microsoftgraph/msgraph-beta-sdk-go/communications"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/models"
	  //other-imports
)

graphClient, err := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphcommunications.NewAnswerPostRequestBody()
callbackUri := "callbackUri-value"
requestBody.SetCallbackUri(&callbackUri) 
mediaConfig := graphmodels.NewMediaConfig()
additionalData := map[string]interface{}{
	"blob" : "<Media Session Configuration Blob>", 
}
mediaConfig.SetAdditionalData(additionalData)
requestBody.SetMediaConfig(mediaConfig)
acceptedModalities := []graphcommunications.Modalityable {
	modality := graphmodels.AUDIO_MODALITY 
	requestBody.SetModality(&modality) 

}
requestBody.SetAcceptedModalities(acceptedModalities)
callOptions := graphmodels.NewIncomingCallOptions()
isContentSharingNotificationEnabled := true
callOptions.SetIsContentSharingNotificationEnabled(&isContentSharingNotificationEnabled) 
requestBody.SetCallOptions(callOptions)
participantCapacity := int32(200)
requestBody.SetParticipantCapacity(&participantCapacity) 

graphClient.Communications().Calls().ByCallId("call-id").Answer().Post(context.Background(), requestBody, nil)


```