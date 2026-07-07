# V1FolderMessagesMessageText

Rendered text and HTML parts of a message.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**text** | **str** |  | 
**html** | **str** |  | 

## Example

```python
from hostinger_email_api.models.v1_folder_messages_message_text import V1FolderMessagesMessageText

# TODO update the JSON string below
json = "{}"
# create an instance of V1FolderMessagesMessageText from a JSON string
v1_folder_messages_message_text_instance = V1FolderMessagesMessageText.from_json(json)
# print the JSON string representation of the object
print(V1FolderMessagesMessageText.to_json())

# convert the object into a dict
v1_folder_messages_message_text_dict = v1_folder_messages_message_text_instance.to_dict()
# create an instance of V1FolderMessagesMessageText from a dict
v1_folder_messages_message_text_from_dict = V1FolderMessagesMessageText.from_dict(v1_folder_messages_message_text_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


