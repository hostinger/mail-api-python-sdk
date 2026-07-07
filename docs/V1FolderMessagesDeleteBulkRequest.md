# V1FolderMessagesDeleteBulkRequest

Body for permanently deleting multiple messages.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uids** | **List[int]** | Message UIDs to delete. 1-100 entries, each &gt; 0. | 

## Example

```python
from hostinger_email_api.models.v1_folder_messages_delete_bulk_request import V1FolderMessagesDeleteBulkRequest

# TODO update the JSON string below
json = "{}"
# create an instance of V1FolderMessagesDeleteBulkRequest from a JSON string
v1_folder_messages_delete_bulk_request_instance = V1FolderMessagesDeleteBulkRequest.from_json(json)
# print the JSON string representation of the object
print(V1FolderMessagesDeleteBulkRequest.to_json())

# convert the object into a dict
v1_folder_messages_delete_bulk_request_dict = v1_folder_messages_delete_bulk_request_instance.to_dict()
# create an instance of V1FolderMessagesDeleteBulkRequest from a dict
v1_folder_messages_delete_bulk_request_from_dict = V1FolderMessagesDeleteBulkRequest.from_dict(v1_folder_messages_delete_bulk_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


