# V1FolderMessagesMoveRequest

Body for moving a single message to a target folder.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**target_folder** | **str** | Destination folder path. | 

## Example

```python
from hostinger_email_api.models.v1_folder_messages_move_request import V1FolderMessagesMoveRequest

# TODO update the JSON string below
json = "{}"
# create an instance of V1FolderMessagesMoveRequest from a JSON string
v1_folder_messages_move_request_instance = V1FolderMessagesMoveRequest.from_json(json)
# print the JSON string representation of the object
print(V1FolderMessagesMoveRequest.to_json())

# convert the object into a dict
v1_folder_messages_move_request_dict = v1_folder_messages_move_request_instance.to_dict()
# create an instance of V1FolderMessagesMoveRequest from a dict
v1_folder_messages_move_request_from_dict = V1FolderMessagesMoveRequest.from_dict(v1_folder_messages_move_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


