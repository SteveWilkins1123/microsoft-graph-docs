---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphdrives "github.com/microsoftgraph/msgraph-beta-sdk-go/drives"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/models"
	  //other-imports
)

graphClient, err := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphdrives.NewInvitePostRequestBody()


driveRecipient := graphmodels.NewDriveRecipient()
email := "robin@contoso.org"
driveRecipient.SetEmail(&email) 

recipients := []graphdrives.DriveRecipientable {
	driveRecipient,

}
requestBody.SetRecipients(recipients)
message := "Here's the file that we're collaborating on."
requestBody.SetMessage(&message) 
requireSignIn := true
requestBody.SetRequireSignIn(&requireSignIn) 
sendInvitation := true
requestBody.SetSendInvitation(&sendInvitation) 
roles := []string {
	"write",

}
requestBody.SetRoles(roles)
password := "password123"
requestBody.SetPassword(&password) 
expirationDateTime := "2018-07-15T14:00:00.000Z"
requestBody.SetExpirationDateTime(&expirationDateTime) 

result, err := graphClient.Drives().ByDriveId("drive-id").Items().ByItemId("driveItem-id").Invite().Post(context.Background(), requestBody, nil)


```