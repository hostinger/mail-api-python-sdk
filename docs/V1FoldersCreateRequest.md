# V1FoldersCreateRequest

Body for creating a folder.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **str** | Folder name. Length 1-100 after trimming. | 

## Example

```python
from hostinger_mail_api.models.v1_folders_create_request import V1FoldersCreateRequest

# TODO update the JSON string below
json = "{}"
# create an instance of V1FoldersCreateRequest from a JSON string
v1_folders_create_request_instance = V1FoldersCreateRequest.from_json(json)
# print the JSON string representation of the object
print(V1FoldersCreateRequest.to_json())

# convert the object into a dict
v1_folders_create_request_dict = v1_folders_create_request_instance.to_dict()
# create an instance of V1FoldersCreateRequest from a dict
v1_folders_create_request_from_dict = V1FoldersCreateRequest.from_dict(v1_folders_create_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


