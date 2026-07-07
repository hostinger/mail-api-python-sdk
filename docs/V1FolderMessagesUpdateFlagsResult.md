# V1FolderMessagesUpdateFlagsResult

Per-UID outcome of a bulk flag update. 200 when every UID succeeded, 207 when at least one failed.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**V1FolderMessagesUpdateFlagsResultData**](V1FolderMessagesUpdateFlagsResultData.md) |  | 

## Example

```python
from hostinger_email_api.models.v1_folder_messages_update_flags_result import V1FolderMessagesUpdateFlagsResult

# TODO update the JSON string below
json = "{}"
# create an instance of V1FolderMessagesUpdateFlagsResult from a JSON string
v1_folder_messages_update_flags_result_instance = V1FolderMessagesUpdateFlagsResult.from_json(json)
# print the JSON string representation of the object
print(V1FolderMessagesUpdateFlagsResult.to_json())

# convert the object into a dict
v1_folder_messages_update_flags_result_dict = v1_folder_messages_update_flags_result_instance.to_dict()
# create an instance of V1FolderMessagesUpdateFlagsResult from a dict
v1_folder_messages_update_flags_result_from_dict = V1FolderMessagesUpdateFlagsResult.from_dict(v1_folder_messages_update_flags_result_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


