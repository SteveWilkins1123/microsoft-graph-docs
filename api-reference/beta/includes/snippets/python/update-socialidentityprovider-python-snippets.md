---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

// THE PYTHON SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
client =  GraphServiceClient(request_adapter)

request_body = IdentityProviderBase()
request_body.@odata_type = '#microsoft.graph.socialIdentityProvider'

additional_data = [
'client_secret' => '1111111111111', 
];
request_body.additional_data(additional_data)





result = await client.identity.identity_providers.by_identity_provider_id('identityProviderBase-id').patch(request_body = request_body)


```