# V1FolderMessagesMessageTextResource

Single message text payload.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**V1FolderMessagesMessageText**](V1FolderMessagesMessageText.md) |  | 

## Example

```python
from hostinger_mail_api.models.v1_folder_messages_message_text_resource import V1FolderMessagesMessageTextResource

# TODO update the JSON string below
json = "{}"
# create an instance of V1FolderMessagesMessageTextResource from a JSON string
v1_folder_messages_message_text_resource_instance = V1FolderMessagesMessageTextResource.from_json(json)
# print the JSON string representation of the object
print(V1FolderMessagesMessageTextResource.to_json())

# convert the object into a dict
v1_folder_messages_message_text_resource_dict = v1_folder_messages_message_text_resource_instance.to_dict()
# create an instance of V1FolderMessagesMessageTextResource from a dict
v1_folder_messages_message_text_resource_from_dict = V1FolderMessagesMessageTextResource.from_dict(v1_folder_messages_message_text_resource_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


