# V1FoldersCollection

Paginated list of folders.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**List[V1FoldersFolder]**](V1FoldersFolder.md) |  | 
**pagination** | [**Pagination**](Pagination.md) |  | 

## Example

```python
from hostinger_email_api.models.v1_folders_collection import V1FoldersCollection

# TODO update the JSON string below
json = "{}"
# create an instance of V1FoldersCollection from a JSON string
v1_folders_collection_instance = V1FoldersCollection.from_json(json)
# print the JSON string representation of the object
print(V1FoldersCollection.to_json())

# convert the object into a dict
v1_folders_collection_dict = v1_folders_collection_instance.to_dict()
# create an instance of V1FoldersCollection from a dict
v1_folders_collection_from_dict = V1FoldersCollection.from_dict(v1_folders_collection_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


