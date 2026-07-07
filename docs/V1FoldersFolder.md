# V1FoldersFolder

A folder (IMAP mailbox) in the managed mailbox.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**path** | **str** | Full hierarchical folder path including the delimiter. | 
**name** | **str** | Leaf name of the folder. | 
**delimiter** | **str** | Hierarchy delimiter used by the IMAP server. | 
**special_use** | **str** | IMAP SPECIAL-USE attribute (RFC 6154). &#x60;null&#x60; for regular folders. | 
**message_count** | **int** | Total number of messages in the folder. | 
**unread_count** | **int** | Number of unread messages in the folder. | 

## Example

```python
from hostinger_email_api.models.v1_folders_folder import V1FoldersFolder

# TODO update the JSON string below
json = "{}"
# create an instance of V1FoldersFolder from a JSON string
v1_folders_folder_instance = V1FoldersFolder.from_json(json)
# print the JSON string representation of the object
print(V1FoldersFolder.to_json())

# convert the object into a dict
v1_folders_folder_dict = v1_folders_folder_instance.to_dict()
# create an instance of V1FoldersFolder from a dict
v1_folders_folder_from_dict = V1FoldersFolder.from_dict(v1_folders_folder_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


