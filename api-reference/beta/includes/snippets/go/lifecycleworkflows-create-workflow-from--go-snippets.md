---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodelsidentitygovernance "github.com/microsoftgraph/msgraph-beta-sdk-go/models/identitygovernance"
	  //other-imports
)

graphClient, err := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodelsidentitygovernance.NewWorkflow()
category := graphmodels.JOINER_LIFECYCLEWORKFLOWCATEGORY 
requestBody.SetCategory(&category) 
description := "Configure new hire tasks for onboarding employees on their first day"
requestBody.SetDescription(&description) 
displayName := "Australia Onboard new hire employee"
requestBody.SetDisplayName(&displayName) 
isEnabled := true
requestBody.SetIsEnabled(&isEnabled) 
isSchedulingEnabled := false
requestBody.SetIsSchedulingEnabled(&isSchedulingEnabled) 
executionConditions := graphmodelsidentitygovernance.NewWorkflowExecutionConditions()
additionalData := map[string]interface{}{
scope := graphmodels.New()
rule := "(country eq 'Australia')"
scope.SetRule(&rule) 
	executionConditions.SetScope(scope)
trigger := graphmodels.New()
timeBasedAttribute := "employeeHireDate"
trigger.SetTimeBasedAttribute(&timeBasedAttribute) 
offsetInDays := int32(0)
trigger.SetOffsetInDays(&offsetInDays) 
	executionConditions.SetTrigger(trigger)
}
executionConditions.SetAdditionalData(additionalData)
requestBody.SetExecutionConditions(executionConditions)


task := graphmodelsidentitygovernance.NewTask()
continueOnError := false
task.SetContinueOnError(&continueOnError) 
description := "Enable user account in the directory"
task.SetDescription(&description) 
displayName := "Enable User Account"
task.SetDisplayName(&displayName) 
isEnabled := true
task.SetIsEnabled(&isEnabled) 
taskDefinitionId := "6fc52c9d-398b-4305-9763-15f42c1676fc"
task.SetTaskDefinitionId(&taskDefinitionId) 
arguments := []graphmodelsidentitygovernance.KeyValuePairable {

}
task.SetArguments(arguments)
task1 := graphmodelsidentitygovernance.NewTask()
continueOnError := false
task1.SetContinueOnError(&continueOnError) 
description := "Send welcome email to new hire"
task1.SetDescription(&description) 
displayName := "Send Welcome Email"
task1.SetDisplayName(&displayName) 
isEnabled := true
task1.SetIsEnabled(&isEnabled) 
taskDefinitionId := "70b29d51-b59a-4773-9280-8841dfd3f2ea"
task1.SetTaskDefinitionId(&taskDefinitionId) 
arguments := []graphmodelsidentitygovernance.KeyValuePairable {

}
task1.SetArguments(arguments)

tasks := []graphmodelsidentitygovernance.Taskable {
	task,
	task1,

}
requestBody.SetTasks(tasks)

result, err := graphClient.IdentityGovernance().LifecycleWorkflows().Workflows().Post(context.Background(), requestBody, nil)


```