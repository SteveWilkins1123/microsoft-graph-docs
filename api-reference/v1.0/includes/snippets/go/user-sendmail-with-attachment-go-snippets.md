---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphusers "github.com/microsoftgraph/msgraph-sdk-go/users"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  //other-imports
)

graphClient, err := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphusers.NewSendMailPostRequestBody()
message := graphmodels.NewMessage()
subject := "Meet for lunch?"
message.SetSubject(&subject) 
body := graphmodels.NewItemBody()
contentType := graphmodels.TEXT_BODYTYPE 
body.SetContentType(&contentType) 
content := "The new cafeteria is open."
body.SetContent(&content) 
message.SetBody(body)


recipient := graphmodels.NewRecipient()
emailAddress := graphmodels.NewEmailAddress()
address := "meganb@contoso.onmicrosoft.com"
emailAddress.SetAddress(&address) 
recipient.SetEmailAddress(emailAddress)

toRecipients := []graphmodels.Recipientable {
	recipient,

}
message.SetToRecipients(toRecipients)


attachment := graphmodels.NewAttachment()
name := "attachment.txt"
attachment.SetName(&name) 
contentType := "text/plain"
attachment.SetContentType(&contentType) 
additionalData := map[string]interface{}{
	"contentBytes" : "SGVsbG8gV29ybGQh", 
}
attachment.SetAdditionalData(additionalData)

attachments := []graphmodels.Attachmentable {
	attachment,

}
message.SetAttachments(attachments)
requestBody.SetMessage(message)

graphClient.Me().SendMail().Post(context.Background(), requestBody, nil)


```