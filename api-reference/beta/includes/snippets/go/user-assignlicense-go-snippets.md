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


requestBody := graphusers.NewAssignLicensePostRequestBody()


assignedLicense := graphmodels.NewAssignedLicense()
disabledPlans := []string {
 := uuid.MustParse("8a256a2b-b617-496d-b51b-e76466e88db0")
assignedLicense.Set(&) 

}
assignedLicense.SetDisabledPlans(disabledPlans)
skuId := uuid.MustParse("84a661c4-e949-4bd2-a560-ed7766fcaf2b")
assignedLicense.SetSkuId(&skuId) 
assignedLicense1 := graphmodels.NewAssignedLicense()
disabledPlans := []string {

}
assignedLicense1.SetDisabledPlans(disabledPlans)
skuId := uuid.MustParse("f30db892-07e9-47e9-837c-80727f46fd3d")
assignedLicense1.SetSkuId(&skuId) 

addLicenses := []graphusers.AssignedLicenseable {
	assignedLicense,
	assignedLicense1,

}
requestBody.SetAddLicenses(addLicenses)
removeLicenses := []string {

}
requestBody.SetRemoveLicenses(removeLicenses)

result, err := graphClient.Me().AssignLicense().Post(context.Background(), requestBody, nil)


```