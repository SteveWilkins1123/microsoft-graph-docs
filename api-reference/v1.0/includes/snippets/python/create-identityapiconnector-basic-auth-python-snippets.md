---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

// THE PYTHON SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
client =  GraphServiceClient(request_adapter)

request_body = IdentityApiConnector()
request_body.display_name = 'Test API'

request_body.target_url = 'https://someapi.com/api'

authentication_configuration = ApiAuthenticationConfigurationBase()
authentication_configuration.@odata_type = '#microsoft.graph.basicAuthentication'

additional_data = [
'username' => 'MyUsername', 
'password' => 'MyPassword', 
];
authentication_configuration.additional_data(additional_data)



request_body.authentication_configuration = authentication_configuration



result = await client.identity.api_connectors.post(request_body = request_body)


```