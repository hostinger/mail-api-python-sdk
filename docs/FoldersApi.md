# hostinger_mail_api.FoldersApi

All URIs are relative to *https://api.mail.hostinger.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_folder**](FoldersApi.md#create_folder) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders | Create folder
[**delete_folder**](FoldersApi.md#delete_folder) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder} | Delete folder
[**list_folders**](FoldersApi.md#list_folders) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders | List folders
[**update_folder**](FoldersApi.md#update_folder) | **PUT** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder} | Update folder


# **create_folder**
> V1FoldersResource create_folder(mailbox_resource_id, v1_folders_create_request)

Create folder

Create a new folder in the managed mailbox.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_folders_create_request import V1FoldersCreateRequest
from hostinger_mail_api.models.v1_folders_resource import V1FoldersResource
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.FoldersApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    v1_folders_create_request = hostinger_mail_api.V1FoldersCreateRequest() # V1FoldersCreateRequest | 

    try:
        # Create folder
        api_response = api_instance.create_folder(mailbox_resource_id, v1_folders_create_request)
        print("The response of FoldersApi->create_folder:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling FoldersApi->create_folder: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **v1_folders_create_request** | [**V1FoldersCreateRequest**](V1FoldersCreateRequest.md)|  | 

### Return type

[**V1FoldersResource**](V1FoldersResource.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Folder created. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**409** | Conflict with the target resource. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_folder**
> delete_folder(mailbox_resource_id, folder)

Delete folder

Delete a folder and all of its subfolders.

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
    api_instance = hostinger_mail_api.FoldersApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    folder = 'INBOX.OldName' # str | Folder path to delete (URL-encoded).

    try:
        # Delete folder
        api_instance.delete_folder(mailbox_resource_id, folder)
    except Exception as e:
        print("Exception when calling FoldersApi->delete_folder: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **folder** | **str**| Folder path to delete (URL-encoded). | 

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
**204** | Folder and all subfolders deleted. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**409** | Conflict with the target resource. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_folders**
> V1FoldersCollection list_folders(mailbox_resource_id, page=page, per_page=per_page)

List folders

Retrieve a paginated list of folders in the managed mailbox.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_folders_collection import V1FoldersCollection
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.FoldersApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    page = 1 # int | Page number (1-based). (optional) (default to 1)
    per_page = 25 # int | Items per page (max 100). (optional) (default to 25)

    try:
        # List folders
        api_response = api_instance.list_folders(mailbox_resource_id, page=page, per_page=per_page)
        print("The response of FoldersApi->list_folders:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling FoldersApi->list_folders: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **page** | **int**| Page number (1-based). | [optional] [default to 1]
 **per_page** | **int**| Items per page (max 100). | [optional] [default to 25]

### Return type

[**V1FoldersCollection**](V1FoldersCollection.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Paginated list of folders. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_folder**
> V1FoldersResource update_folder(mailbox_resource_id, folder, v1_folders_update_request)

Update folder

Rename an existing folder.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_folders_resource import V1FoldersResource
from hostinger_mail_api.models.v1_folders_update_request import V1FoldersUpdateRequest
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.FoldersApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    folder = 'INBOX.OldName' # str | Current folder path (URL-encoded).
    v1_folders_update_request = hostinger_mail_api.V1FoldersUpdateRequest() # V1FoldersUpdateRequest | 

    try:
        # Update folder
        api_response = api_instance.update_folder(mailbox_resource_id, folder, v1_folders_update_request)
        print("The response of FoldersApi->update_folder:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling FoldersApi->update_folder: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **folder** | **str**| Current folder path (URL-encoded). | 
 **v1_folders_update_request** | [**V1FoldersUpdateRequest**](V1FoldersUpdateRequest.md)|  | 

### Return type

[**V1FoldersResource**](V1FoldersResource.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Folder renamed. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**409** | Conflict with the target resource. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

