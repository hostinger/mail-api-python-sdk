# V1FolderMessagesResource

Single message payload.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**V1FolderMessagesMessage**](V1FolderMessagesMessage.md) |  | 

## Example

```python
from hostinger_email_api.models.v1_folder_messages_resource import V1FolderMessagesResource

# TODO update the JSON string below
json = "{}"
# create an instance of V1FolderMessagesResource from a JSON string
v1_folder_messages_resource_instance = V1FolderMessagesResource.from_json(json)
# print the JSON string representation of the object
print(V1FolderMessagesResource.to_json())

# convert the object into a dict
v1_folder_messages_resource_dict = v1_folder_messages_resource_instance.to_dict()
# create an instance of V1FolderMessagesResource from a dict
v1_folder_messages_resource_from_dict = V1FolderMessagesResource.from_dict(v1_folder_messages_resource_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


