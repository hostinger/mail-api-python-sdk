# V1FoldersUpdateRequest

Body for renaming a folder.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** | New folder name. Length 1-100 after trimming. | 

## Example

```python
from hostinger_email_api.models.v1_folders_update_request import V1FoldersUpdateRequest

# TODO update the JSON string below
json = "{}"
# create an instance of V1FoldersUpdateRequest from a JSON string
v1_folders_update_request_instance = V1FoldersUpdateRequest.from_json(json)
# print the JSON string representation of the object
print(V1FoldersUpdateRequest.to_json())

# convert the object into a dict
v1_folders_update_request_dict = v1_folders_update_request_instance.to_dict()
# create an instance of V1FoldersUpdateRequest from a dict
v1_folders_update_request_from_dict = V1FoldersUpdateRequest.from_dict(v1_folders_update_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


