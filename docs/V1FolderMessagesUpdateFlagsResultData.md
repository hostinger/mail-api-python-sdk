# V1FolderMessagesUpdateFlagsResultData


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**successful** | **List[int]** |  | 
**failed** | [**List[V1FolderMessagesUpdateFlagsResultDataFailedInner]**](V1FolderMessagesUpdateFlagsResultDataFailedInner.md) |  | 

## Example

```python
from hostinger_email_api.models.v1_folder_messages_update_flags_result_data import V1FolderMessagesUpdateFlagsResultData

# TODO update the JSON string below
json = "{}"
# create an instance of V1FolderMessagesUpdateFlagsResultData from a JSON string
v1_folder_messages_update_flags_result_data_instance = V1FolderMessagesUpdateFlagsResultData.from_json(json)
# print the JSON string representation of the object
print(V1FolderMessagesUpdateFlagsResultData.to_json())

# convert the object into a dict
v1_folder_messages_update_flags_result_data_dict = v1_folder_messages_update_flags_result_data_instance.to_dict()
# create an instance of V1FolderMessagesUpdateFlagsResultData from a dict
v1_folder_messages_update_flags_result_data_from_dict = V1FolderMessagesUpdateFlagsResultData.from_dict(v1_folder_messages_update_flags_result_data_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


