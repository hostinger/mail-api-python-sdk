# V1SendRequest

Outgoing message payload. At least one of to, cc, or bcc must be present.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**to** | **List[str]** |  | [optional] 
**display_name** | **str** |  | [optional] 
**cc** | **List[str]** |  | [optional] 
**bcc** | **List[str]** |  | [optional] 
**subject** | **str** |  | [optional] 
**text** | **str** |  | [optional] 
**html** | **str** |  | [optional] 
**attachments** | [**List[V1SendAttachment]**](V1SendAttachment.md) |  | [optional] 
**in_reply_to** | [**V1SendMessageRef**](V1SendMessageRef.md) | Source message this is a reply to. Copies its Message-Id/References into In-Reply-To/References and flags it \\Answered. Mutually exclusive with forwardOf. | [optional] 
**forward_of** | [**V1SendMessageRef**](V1SendMessageRef.md) | Source message this forwards. Copies its Message-Id/References into In-Reply-To/References and flags it $forwarded. Mutually exclusive with inReplyTo. | [optional] 

## Example

```python
from hostinger_mail_api.models.v1_send_request import V1SendRequest

# TODO update the JSON string below
json = "{}"
# create an instance of V1SendRequest from a JSON string
v1_send_request_instance = V1SendRequest.from_json(json)
# print the JSON string representation of the object
print(V1SendRequest.to_json())

# convert the object into a dict
v1_send_request_dict = v1_send_request_instance.to_dict()
# create an instance of V1SendRequest from a dict
v1_send_request_from_dict = V1SendRequest.from_dict(v1_send_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


