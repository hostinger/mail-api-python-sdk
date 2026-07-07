# V1FolderMessagesMoveBulkRequest

Body for moving multiple messages to a target folder.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uids** | **List[int]** | Message UIDs to move. 1-100 entries, each &gt; 0. | 
**target_folder** | **str** | Destination folder path. | 

## Example

```python
from hostinger_email_api.models.v1_folder_messages_move_bulk_request import V1FolderMessagesMoveBulkRequest

# TODO update the JSON string below
json = "{}"
# create an instance of V1FolderMessagesMoveBulkRequest from a JSON string
v1_folder_messages_move_bulk_request_instance = V1FolderMessagesMoveBulkRequest.from_json(json)
# print the JSON string representation of the object
print(V1FolderMessagesMoveBulkRequest.to_json())

# convert the object into a dict
v1_folder_messages_move_bulk_request_dict = v1_folder_messages_move_bulk_request_instance.to_dict()
# create an instance of V1FolderMessagesMoveBulkRequest from a dict
v1_folder_messages_move_bulk_request_from_dict = V1FolderMessagesMoveBulkRequest.from_dict(v1_folder_messages_move_bulk_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


