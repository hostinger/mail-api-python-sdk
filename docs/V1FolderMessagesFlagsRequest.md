# V1FolderMessagesFlagsRequest

Add and/or remove flags on a message. At least one of addFlags or removeFlags must be set.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**add_flags** | **List[str]** |  | [optional] 
**remove_flags** | **List[str]** |  | [optional] 

## Example

```python
from hostinger_mail_api.models.v1_folder_messages_flags_request import V1FolderMessagesFlagsRequest

# TODO update the JSON string below
json = "{}"
# create an instance of V1FolderMessagesFlagsRequest from a JSON string
v1_folder_messages_flags_request_instance = V1FolderMessagesFlagsRequest.from_json(json)
# print the JSON string representation of the object
print(V1FolderMessagesFlagsRequest.to_json())

# convert the object into a dict
v1_folder_messages_flags_request_dict = v1_folder_messages_flags_request_instance.to_dict()
# create an instance of V1FolderMessagesFlagsRequest from a dict
v1_folder_messages_flags_request_from_dict = V1FolderMessagesFlagsRequest.from_dict(v1_folder_messages_flags_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


