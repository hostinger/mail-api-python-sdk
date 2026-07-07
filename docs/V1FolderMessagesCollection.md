# V1FolderMessagesCollection

Paginated list of messages.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**List[V1FolderMessagesMessage]**](V1FolderMessagesMessage.md) |  | 
**pagination** | [**Pagination**](Pagination.md) |  | 

## Example

```python
from hostinger_email_api.models.v1_folder_messages_collection import V1FolderMessagesCollection

# TODO update the JSON string below
json = "{}"
# create an instance of V1FolderMessagesCollection from a JSON string
v1_folder_messages_collection_instance = V1FolderMessagesCollection.from_json(json)
# print the JSON string representation of the object
print(V1FolderMessagesCollection.to_json())

# convert the object into a dict
v1_folder_messages_collection_dict = v1_folder_messages_collection_instance.to_dict()
# create an instance of V1FolderMessagesCollection from a dict
v1_folder_messages_collection_from_dict = V1FolderMessagesCollection.from_dict(v1_folder_messages_collection_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


