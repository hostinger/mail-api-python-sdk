# V1FolderMessagesSearchRequest

Search criteria. All fields optional; combine to narrow results.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**since** | **date** |  | [optional] 
**before** | **date** |  | [optional] 
**flags** | **List[str]** |  | [optional] 
**uid** | **str** |  | [optional] 
**subject** | **str** |  | [optional] 
**var_from** | **str** |  | [optional] 
**to** | **str** |  | [optional] 
**cc** | **str** |  | [optional] 
**body** | **str** |  | [optional] 
**header** | **str** |  | [optional] 
**larger** | **int** |  | [optional] 
**smaller** | **int** |  | [optional] 
**text** | **str** |  | [optional] 

## Example

```python
from hostinger_email_api.models.v1_folder_messages_search_request import V1FolderMessagesSearchRequest

# TODO update the JSON string below
json = "{}"
# create an instance of V1FolderMessagesSearchRequest from a JSON string
v1_folder_messages_search_request_instance = V1FolderMessagesSearchRequest.from_json(json)
# print the JSON string representation of the object
print(V1FolderMessagesSearchRequest.to_json())

# convert the object into a dict
v1_folder_messages_search_request_dict = v1_folder_messages_search_request_instance.to_dict()
# create an instance of V1FolderMessagesSearchRequest from a dict
v1_folder_messages_search_request_from_dict = V1FolderMessagesSearchRequest.from_dict(v1_folder_messages_search_request_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


