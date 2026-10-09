# V1FolderMessagesSearchRequest

Search criteria. All fields optional. subject, from, to, cc and body are alternatives (a message matching any one of them qualifies); all other fields are combined with AND.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**since** | **date** | Only messages received on or after this date (YYYY-MM-DD). | [optional] 
**before** | **date** | Only messages received before this date (YYYY-MM-DD). | [optional] 
**flags** | **List[str]** | Only messages carrying all of these IMAP flags, e.g. \\Seen, \\Flagged, \\Answered, $forwarded. | [optional] 
**uid** | **str** | IMAP UID set: single UID, range (1:100), open range (100:*), or comma-separated list. | [optional] 
**subject** | **str** | Case-insensitive substring match on the Subject header. OR-combined with from/to/cc/body. | [optional] 
**var_from** | **str** | Case-insensitive substring match on the From header. OR-combined with subject/to/cc/body. | [optional] 
**to** | **str** | Case-insensitive substring match on the To header. OR-combined with subject/from/cc/body. | [optional] 
**cc** | **str** | Case-insensitive substring match on the Cc header. OR-combined with subject/from/to/body. | [optional] 
**body** | **str** | Case-insensitive substring match on the message body only (headers excluded). OR-combined with subject/from/to/cc. | [optional] 
**header** | **str** | Match a specific header as Name:value, e.g. X-Custom-Header:value. Value match is a substring. | [optional] 
**larger** | **int** | Only messages larger than this size in bytes. | [optional] 
**smaller** | **int** | Only messages smaller than this size in bytes. | [optional] 
**text** | **str** | Case-insensitive substring match across headers and body. | [optional] 

## Example

```python
from hostinger_mail_api.models.v1_folder_messages_search_request import V1FolderMessagesSearchRequest

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


