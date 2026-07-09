# V1FolderMessagesFlagsBulkRequest

Add and/or remove flags on multiple messages. At least one of addFlags or removeFlags must be set.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uids** | **List[int]** | Message UIDs to update. 1-100 entries, each &gt; 0. | 
**add_flags** | **List[str]** |  | [optional] 
**remove_flags** | **List[str]** |  | [optional] 

## Example

```python
from hostinger_mail_api.models.v1_folder_messages_flags_bulk_request import V1FolderMessagesFlagsBulkRequest

# TODO update the JSON string below
json = "{}"
# create an instance of V1FolderMessagesFlagsBulkRequest from a JSON string
v1_folder_messages_flags_bulk_request_instance = V1FolderMessagesFlagsBulkRequest.from_json(json)
# print the JSON string representation of the object
print(V1FolderMessagesFlagsBulkRequest.to_json())

# convert the object into a dict
v1_folder_messages_flags_bulk_request_dict = v1_folder_messages_flags_bulk_request_instance.to_dict()
# create an instance of V1FolderMessagesFlagsBulkRequest from a dict
v1_folder_messages_flags_bulk_request_from_dict = V1FolderMessagesFlagsBulkRequest.from_dict(v1_folder_messages_flags_bulk_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


