---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

// THE PYTHON SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
client =  GraphServiceClient(request_adapter)

request_body = ConversationMember()
request_body.@odata_type = '#microsoft.graph.aadUserConversationMember'

request_body.visibleHistoryStartDateTime = DateTime('2019-04-18T23:51:43.255Z')

request_body.Roles(['owner', ])

additional_data = [
'user@odata_bind' => 'https://graph.microsoft.com/beta/users/jacob@contoso.com', 
];
request_body.additional_data(additional_data)





result = await client.chats.by_chat_id('chat-id').members.post(request_body = request_body)


```