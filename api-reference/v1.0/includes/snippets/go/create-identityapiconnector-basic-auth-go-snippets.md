---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  //other-imports
)

graphClient, err := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewIdentityApiConnector()
displayName := "Test API"
requestBody.SetDisplayName(&displayName) 
targetUrl := "https://someapi.com/api"
requestBody.SetTargetUrl(&targetUrl) 
authenticationConfiguration := graphmodels.NewApiAuthenticationConfigurationBase()
additionalData := map[string]interface{}{
	"username" : "MyUsername", 
	"password" : "MyPassword", 
}
authenticationConfiguration.SetAdditionalData(additionalData)
requestBody.SetAuthenticationConfiguration(authenticationConfiguration)

result, err := graphClient.Identity().ApiConnectors().Post(context.Background(), requestBody, nil)


```