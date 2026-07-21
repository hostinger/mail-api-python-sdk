# V1SendMessageRef

Reference to a source message by UID within a folder, used for reply/forward threading. Both fields are required.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uid** | **int** | UID of the source message. | 
**folder** | **str** | Folder containing the source message. | 

## Example

```python
from hostinger_mail_api.models.v1_send_message_ref import V1SendMessageRef

# TODO update the JSON string below
json = "{}"
# create an instance of V1SendMessageRef from a JSON string
v1_send_message_ref_instance = V1SendMessageRef.from_json(json)
# print the JSON string representation of the object
print(V1SendMessageRef.to_json())

# convert the object into a dict
v1_send_message_ref_dict = v1_send_message_ref_instance.to_dict()
# create an instance of V1SendMessageRef from a dict
v1_send_message_ref_from_dict = V1SendMessageRef.from_dict(v1_send_message_ref_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


