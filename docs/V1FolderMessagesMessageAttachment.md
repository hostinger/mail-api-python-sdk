# V1FolderMessagesMessageAttachment

Attachment metadata attached to a message.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **str** | Opaque attachment identifier. Use as the {attachmentId} path parameter on the download endpoint. | 
**content_type** | **str** |  | 
**size_bytes** | **int** |  | 
**inline** | **bool** |  | 
**filename** | **str** |  | 
**content_id** | **str** |  | 

## Example

```python
from hostinger_email_api.models.v1_folder_messages_message_attachment import V1FolderMessagesMessageAttachment

# TODO update the JSON string below
json = "{}"
# create an instance of V1FolderMessagesMessageAttachment from a JSON string
v1_folder_messages_message_attachment_instance = V1FolderMessagesMessageAttachment.from_json(json)
# print the JSON string representation of the object
print(V1FolderMessagesMessageAttachment.to_json())

# convert the object into a dict
v1_folder_messages_message_attachment_dict = v1_folder_messages_message_attachment_instance.to_dict()
# create an instance of V1FolderMessagesMessageAttachment from a dict
v1_folder_messages_message_attachment_from_dict = V1FolderMessagesMessageAttachment.from_dict(v1_folder_messages_message_attachment_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


