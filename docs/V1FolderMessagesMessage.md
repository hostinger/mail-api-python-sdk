# V1FolderMessagesMessage

A message in a folder of the managed mailbox.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uid** | **int** |  | 
**path** | **str** |  | 
**var_date** | **datetime** |  | 
**flags** | **List[str]** |  | 
**unseen** | **bool** |  | 
**size** | **int** |  | 
**subject** | **str** |  | 
**var_from** | [**V1FolderMessagesMessageAddress**](V1FolderMessagesMessageAddress.md) |  | 
**to** | [**List[V1FolderMessagesMessageAddress]**](V1FolderMessagesMessageAddress.md) |  | 
**cc** | [**List[V1FolderMessagesMessageAddress]**](V1FolderMessagesMessageAddress.md) |  | 
**bcc** | [**List[V1FolderMessagesMessageAddress]**](V1FolderMessagesMessageAddress.md) |  | 
**message_id** | **str** |  | 
**in_reply_to** | **str** |  | 
**attachments** | [**List[V1FolderMessagesMessageAttachment]**](V1FolderMessagesMessageAttachment.md) |  | 

## Example

```python
from hostinger_mail_api.models.v1_folder_messages_message import V1FolderMessagesMessage

# TODO update the JSON string below
json = "{}"
# create an instance of V1FolderMessagesMessage from a JSON string
v1_folder_messages_message_instance = V1FolderMessagesMessage.from_json(json)
# print the JSON string representation of the object
print(V1FolderMessagesMessage.to_json())

# convert the object into a dict
v1_folder_messages_message_dict = v1_folder_messages_message_instance.to_dict()
# create an instance of V1FolderMessagesMessage from a dict
v1_folder_messages_message_from_dict = V1FolderMessagesMessage.from_dict(v1_folder_messages_message_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


