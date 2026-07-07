# V1FolderMessagesMessageAddress

A single email address with optional display name.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** |  | 
**address** | **str** |  | 

## Example

```python
from hostinger_email_api.models.v1_folder_messages_message_address import V1FolderMessagesMessageAddress

# TODO update the JSON string below
json = "{}"
# create an instance of V1FolderMessagesMessageAddress from a JSON string
v1_folder_messages_message_address_instance = V1FolderMessagesMessageAddress.from_json(json)
# print the JSON string representation of the object
print(V1FolderMessagesMessageAddress.to_json())

# convert the object into a dict
v1_folder_messages_message_address_dict = v1_folder_messages_message_address_instance.to_dict()
# create an instance of V1FolderMessagesMessageAddress from a dict
v1_folder_messages_message_address_from_dict = V1FolderMessagesMessageAddress.from_dict(v1_folder_messages_message_address_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


