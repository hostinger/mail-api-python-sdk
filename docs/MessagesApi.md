# hostinger_mail_api.MessagesApi

All URIs are relative to *https://api.mail.hostinger.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**delete_all_messages**](MessagesApi.md#delete_all_messages) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages | Delete all messages
[**delete_message**](MessagesApi.md#delete_message) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid} | Delete message
[**delete_messages**](MessagesApi.md#delete_messages) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/delete | Delete messages
[**get_message**](MessagesApi.md#get_message) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid} | Get message
[**get_message_attachment**](MessagesApi.md#get_message_attachment) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid}/attachments/{attachmentId} | Download message attachment
[**get_message_source**](MessagesApi.md#get_message_source) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid}/source | Get message source
[**get_message_text**](MessagesApi.md#get_message_text) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid}/text | Get message text content
[**list_messages**](MessagesApi.md#list_messages) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages | List messages
[**move_message**](MessagesApi.md#move_message) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid}/move | Move message
[**move_messages**](MessagesApi.md#move_messages) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/move | Move messages
[**patch_message**](MessagesApi.md#patch_message) | **PATCH** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid} | Update message flags
[**search_messages**](MessagesApi.md#search_messages) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/search | Search messages
[**update_message_flags**](MessagesApi.md#update_message_flags) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/flags | Update message flags


# **delete_all_messages**
> delete_all_messages(mailbox_resource_id, folder)

Delete all messages

Permanently delete every message in a folder (empty the folder).

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.MessagesApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    folder = 'INBOX.Trash' # str | Folder path (URL-encoded).

    try:
        # Delete all messages
        api_instance.delete_all_messages(mailbox_resource_id, folder)
    except Exception as e:
        print("Exception when calling MessagesApi->delete_all_messages: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **folder** | **str**| Folder path (URL-encoded). | 

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Messages deleted successfully. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_message**
> delete_message(mailbox_resource_id, folder, uid)

Delete message

Permanently delete a single message.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.MessagesApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    folder = 'INBOX' # str | Folder path (URL-encoded).
    uid = 42 # int | Message UID.

    try:
        # Delete message
        api_instance.delete_message(mailbox_resource_id, folder, uid)
    except Exception as e:
        print("Exception when calling MessagesApi->delete_message: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **folder** | **str**| Folder path (URL-encoded). | 
 **uid** | **int**| Message UID. | 

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Message deleted successfully. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_messages**
> delete_messages(mailbox_resource_id, folder, v1_folder_messages_delete_bulk_request)

Delete messages

Permanently delete multiple messages from a folder.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_folder_messages_delete_bulk_request import V1FolderMessagesDeleteBulkRequest
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.MessagesApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    folder = 'INBOX' # str | Folder path (URL-encoded).
    v1_folder_messages_delete_bulk_request = hostinger_mail_api.V1FolderMessagesDeleteBulkRequest() # V1FolderMessagesDeleteBulkRequest | 

    try:
        # Delete messages
        api_instance.delete_messages(mailbox_resource_id, folder, v1_folder_messages_delete_bulk_request)
    except Exception as e:
        print("Exception when calling MessagesApi->delete_messages: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **folder** | **str**| Folder path (URL-encoded). | 
 **v1_folder_messages_delete_bulk_request** | [**V1FolderMessagesDeleteBulkRequest**](V1FolderMessagesDeleteBulkRequest.md)|  | 

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Messages deleted successfully. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_message**
> V1FolderMessagesResource get_message(mailbox_resource_id, folder, uid)

Get message

Retrieve a single message by UID.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_folder_messages_resource import V1FolderMessagesResource
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.MessagesApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    folder = 'INBOX' # str | Folder path (URL-encoded).
    uid = 42 # int | Message UID.

    try:
        # Get message
        api_response = api_instance.get_message(mailbox_resource_id, folder, uid)
        print("The response of MessagesApi->get_message:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MessagesApi->get_message: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **folder** | **str**| Folder path (URL-encoded). | 
 **uid** | **int**| Message UID. | 

### Return type

[**V1FolderMessagesResource**](V1FolderMessagesResource.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Message payload. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_message_attachment**
> bytearray get_message_attachment(mailbox_resource_id, folder, uid, attachment_id)

Download message attachment

Download a message attachment as `application/octet-stream`.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.MessagesApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    folder = 'INBOX' # str | Folder path (URL-encoded).
    uid = 42 # int | Message UID.
    attachment_id = 'YXR0YWNobWVudDpJTkJPWDoxMjM6MS4y' # str | Attachment ID (opaque, returned by GET message).

    try:
        # Download message attachment
        api_response = api_instance.get_message_attachment(mailbox_resource_id, folder, uid, attachment_id)
        print("The response of MessagesApi->get_message_attachment:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MessagesApi->get_message_attachment: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **folder** | **str**| Folder path (URL-encoded). | 
 **uid** | **int**| Message UID. | 
 **attachment_id** | **str**| Attachment ID (opaque, returned by GET message). | 

### Return type

**bytearray**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/octet-stream, application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Decoded attachment body. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_message_source**
> bytearray get_message_source(mailbox_resource_id, folder, uid)

Get message source

Retrieve raw RFC822 source of a message as `message/rfc822` attachment.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.MessagesApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    folder = 'INBOX' # str | Folder path (URL-encoded).
    uid = 42 # int | Message UID.

    try:
        # Get message source
        api_response = api_instance.get_message_source(mailbox_resource_id, folder, uid)
        print("The response of MessagesApi->get_message_source:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MessagesApi->get_message_source: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **folder** | **str**| Folder path (URL-encoded). | 
 **uid** | **int**| Message UID. | 

### Return type

**bytearray**

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: message/rfc822, application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Raw RFC822 source. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_message_text**
> V1FolderMessagesMessageTextResource get_message_text(mailbox_resource_id, folder, uid)

Get message text content

Retrieve rendered text (plain + HTML) of a message. Marks message as `\Seen`.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_folder_messages_message_text_resource import V1FolderMessagesMessageTextResource
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.MessagesApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    folder = 'INBOX' # str | Folder path (URL-encoded).
    uid = 42 # int | Message UID.

    try:
        # Get message text content
        api_response = api_instance.get_message_text(mailbox_resource_id, folder, uid)
        print("The response of MessagesApi->get_message_text:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MessagesApi->get_message_text: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **folder** | **str**| Folder path (URL-encoded). | 
 **uid** | **int**| Message UID. | 

### Return type

[**V1FolderMessagesMessageTextResource**](V1FolderMessagesMessageTextResource.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Rendered text and HTML payload. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_messages**
> V1FolderMessagesCollection list_messages(mailbox_resource_id, folder, page=page, per_page=per_page, sort=sort)

List messages

List messages in a folder. Use POST /search for filtering. Sort fields: uid, date, size (prefix with `-` for descending). Default `-uid`.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_folder_messages_collection import V1FolderMessagesCollection
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.MessagesApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    folder = 'INBOX' # str | Folder path (URL-encoded).
    page = 1 # int | Page number (1-based). (optional) (default to 1)
    per_page = 25 # int | Items per page (max 100). (optional) (default to 25)
    sort = '-uid' # str | Sort field with optional `-` prefix for descending. Allowed: uid, date, size. (optional) (default to '-uid')

    try:
        # List messages
        api_response = api_instance.list_messages(mailbox_resource_id, folder, page=page, per_page=per_page, sort=sort)
        print("The response of MessagesApi->list_messages:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MessagesApi->list_messages: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **folder** | **str**| Folder path (URL-encoded). | 
 **page** | **int**| Page number (1-based). | [optional] [default to 1]
 **per_page** | **int**| Items per page (max 100). | [optional] [default to 25]
 **sort** | **str**| Sort field with optional &#x60;-&#x60; prefix for descending. Allowed: uid, date, size. | [optional] [default to &#39;-uid&#39;]

### Return type

[**V1FolderMessagesCollection**](V1FolderMessagesCollection.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Paginated list of messages. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **move_message**
> move_message(mailbox_resource_id, folder, uid, v1_folder_messages_move_request)

Move message

Move a single message to a target folder.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_folder_messages_move_request import V1FolderMessagesMoveRequest
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.MessagesApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    folder = 'INBOX' # str | Source folder path (URL-encoded).
    uid = 42 # int | Message UID.
    v1_folder_messages_move_request = hostinger_mail_api.V1FolderMessagesMoveRequest() # V1FolderMessagesMoveRequest | 

    try:
        # Move message
        api_instance.move_message(mailbox_resource_id, folder, uid, v1_folder_messages_move_request)
    except Exception as e:
        print("Exception when calling MessagesApi->move_message: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **folder** | **str**| Source folder path (URL-encoded). | 
 **uid** | **int**| Message UID. | 
 **v1_folder_messages_move_request** | [**V1FolderMessagesMoveRequest**](V1FolderMessagesMoveRequest.md)|  | 

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Message moved successfully. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **move_messages**
> move_messages(mailbox_resource_id, folder, v1_folder_messages_move_bulk_request)

Move messages

Move multiple messages from a source folder to a target folder.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_folder_messages_move_bulk_request import V1FolderMessagesMoveBulkRequest
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.MessagesApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    folder = 'INBOX' # str | Source folder path (URL-encoded).
    v1_folder_messages_move_bulk_request = hostinger_mail_api.V1FolderMessagesMoveBulkRequest() # V1FolderMessagesMoveBulkRequest | 

    try:
        # Move messages
        api_instance.move_messages(mailbox_resource_id, folder, v1_folder_messages_move_bulk_request)
    except Exception as e:
        print("Exception when calling MessagesApi->move_messages: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **folder** | **str**| Source folder path (URL-encoded). | 
 **v1_folder_messages_move_bulk_request** | [**V1FolderMessagesMoveBulkRequest**](V1FolderMessagesMoveBulkRequest.md)|  | 

### Return type

void (empty response body)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**204** | Messages moved successfully. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **patch_message**
> V1FolderMessagesResource patch_message(mailbox_resource_id, folder, uid, v1_folder_messages_flags_request)

Update message flags

Add and/or remove flags on a single message. Returns the updated message.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_folder_messages_flags_request import V1FolderMessagesFlagsRequest
from hostinger_mail_api.models.v1_folder_messages_resource import V1FolderMessagesResource
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.MessagesApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    folder = 'INBOX' # str | Folder path (URL-encoded).
    uid = 42 # int | Message UID.
    v1_folder_messages_flags_request = hostinger_mail_api.V1FolderMessagesFlagsRequest() # V1FolderMessagesFlagsRequest | 

    try:
        # Update message flags
        api_response = api_instance.patch_message(mailbox_resource_id, folder, uid, v1_folder_messages_flags_request)
        print("The response of MessagesApi->patch_message:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MessagesApi->patch_message: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **folder** | **str**| Folder path (URL-encoded). | 
 **uid** | **int**| Message UID. | 
 **v1_folder_messages_flags_request** | [**V1FolderMessagesFlagsRequest**](V1FolderMessagesFlagsRequest.md)|  | 

### Return type

[**V1FolderMessagesResource**](V1FolderMessagesResource.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Updated message. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **search_messages**
> V1FolderMessagesCollection search_messages(mailbox_resource_id, folder, page=page, per_page=per_page, sort=sort, v1_folder_messages_search_request=v1_folder_messages_search_request)

Search messages

Search messages in a folder. Filters in body; pagination and sort via query (`page`, `perPage`, `sort`).

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_folder_messages_collection import V1FolderMessagesCollection
from hostinger_mail_api.models.v1_folder_messages_search_request import V1FolderMessagesSearchRequest
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.MessagesApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    folder = 'INBOX' # str | Folder path (URL-encoded).
    page = 1 # int |  (optional) (default to 1)
    per_page = 25 # int |  (optional) (default to 25)
    sort = '-uid' # str |  (optional) (default to '-uid')
    v1_folder_messages_search_request = hostinger_mail_api.V1FolderMessagesSearchRequest() # V1FolderMessagesSearchRequest |  (optional)

    try:
        # Search messages
        api_response = api_instance.search_messages(mailbox_resource_id, folder, page=page, per_page=per_page, sort=sort, v1_folder_messages_search_request=v1_folder_messages_search_request)
        print("The response of MessagesApi->search_messages:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MessagesApi->search_messages: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **folder** | **str**| Folder path (URL-encoded). | 
 **page** | **int**|  | [optional] [default to 1]
 **per_page** | **int**|  | [optional] [default to 25]
 **sort** | **str**|  | [optional] [default to &#39;-uid&#39;]
 **v1_folder_messages_search_request** | [**V1FolderMessagesSearchRequest**](V1FolderMessagesSearchRequest.md)|  | [optional] 

### Return type

[**V1FolderMessagesCollection**](V1FolderMessagesCollection.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Paginated list of matching messages. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_message_flags**
> V1FolderMessagesUpdateFlagsResult update_message_flags(mailbox_resource_id, folder, v1_folder_messages_flags_bulk_request)

Update message flags

Add and/or remove flags on multiple messages. Returns 200 when all UIDs succeed, 207 with per-UID outcome when some fail.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_folder_messages_flags_bulk_request import V1FolderMessagesFlagsBulkRequest
from hostinger_mail_api.models.v1_folder_messages_update_flags_result import V1FolderMessagesUpdateFlagsResult
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.MessagesApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    folder = 'INBOX' # str | Folder path (URL-encoded).
    v1_folder_messages_flags_bulk_request = hostinger_mail_api.V1FolderMessagesFlagsBulkRequest() # V1FolderMessagesFlagsBulkRequest | 

    try:
        # Update message flags
        api_response = api_instance.update_message_flags(mailbox_resource_id, folder, v1_folder_messages_flags_bulk_request)
        print("The response of MessagesApi->update_message_flags:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling MessagesApi->update_message_flags: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **folder** | **str**| Folder path (URL-encoded). | 
 **v1_folder_messages_flags_bulk_request** | [**V1FolderMessagesFlagsBulkRequest**](V1FolderMessagesFlagsBulkRequest.md)|  | 

### Return type

[**V1FolderMessagesUpdateFlagsResult**](V1FolderMessagesUpdateFlagsResult.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | All UIDs updated successfully. |  -  |
**207** | Some UIDs failed; see body for per-UID outcome. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

