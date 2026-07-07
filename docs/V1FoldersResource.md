# V1FoldersResource

Single folder payload.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**V1FoldersFolder**](V1FoldersFolder.md) |  | 

## Example

```python
from hostinger_email_api.models.v1_folders_resource import V1FoldersResource

# TODO update the JSON string below
json = "{}"
# create an instance of V1FoldersResource from a JSON string
v1_folders_resource_instance = V1FoldersResource.from_json(json)
# print the JSON string representation of the object
print(V1FoldersResource.to_json())

# convert the object into a dict
v1_folders_resource_dict = v1_folders_resource_instance.to_dict()
# create an instance of V1FoldersResource from a dict
v1_folders_resource_from_dict = V1FoldersResource.from_dict(v1_folders_resource_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


