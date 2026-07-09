# hostinger_mail_api.WebhooksApi

All URIs are relative to *https://api.mail.hostinger.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_webhook**](WebhooksApi.md#create_webhook) | **POST** /api/v1/mailboxes/{mailboxResourceId}/webhooks | Create webhook
[**delete_webhook**](WebhooksApi.md#delete_webhook) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook} | Delete webhook
[**get_webhook**](WebhooksApi.md#get_webhook) | **GET** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook} | Get webhook
[**list_webhooks**](WebhooksApi.md#list_webhooks) | **GET** /api/v1/mailboxes/{mailboxResourceId}/webhooks | List webhooks
[**regenerate_webhook_secret**](WebhooksApi.md#regenerate_webhook_secret) | **POST** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook}/regenerate-secret | Regenerate webhook secret
[**test_webhook**](WebhooksApi.md#test_webhook) | **POST** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook}/test | Test webhook
[**update_webhook**](WebhooksApi.md#update_webhook) | **PATCH** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook} | Update webhook


# **create_webhook**
> V1WebhooksResourceWithSecret create_webhook(mailbox_resource_id, v1_webhooks_create_request)

Create webhook

Create a webhook. The response includes the one-time `secret` — store it securely as it is never returned again.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_webhooks_create_request import V1WebhooksCreateRequest
from hostinger_mail_api.models.v1_webhooks_resource_with_secret import V1WebhooksResourceWithSecret
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.WebhooksApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    v1_webhooks_create_request = hostinger_mail_api.V1WebhooksCreateRequest() # V1WebhooksCreateRequest | 

    try:
        # Create webhook
        api_response = api_instance.create_webhook(mailbox_resource_id, v1_webhooks_create_request)
        print("The response of WebhooksApi->create_webhook:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling WebhooksApi->create_webhook: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **v1_webhooks_create_request** | [**V1WebhooksCreateRequest**](V1WebhooksCreateRequest.md)|  | 

### Return type

[**V1WebhooksResourceWithSecret**](V1WebhooksResourceWithSecret.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Webhook created. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_webhook**
> delete_webhook(mailbox_resource_id, webhook)

Delete webhook

Delete a webhook.

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
    api_instance = hostinger_mail_api.WebhooksApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox.
    webhook = '019683f8-1234-7abc-8def-0123456789ab' # str | Webhook identifier (UUID v7).

    try:
        # Delete webhook
        api_instance.delete_webhook(mailbox_resource_id, webhook)
    except Exception as e:
        print("Exception when calling WebhooksApi->delete_webhook: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox. | 
 **webhook** | **str**| Webhook identifier (UUID v7). | 

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
**204** | Webhook deleted. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_webhook**
> V1WebhooksResource get_webhook(mailbox_resource_id, webhook)

Get webhook

Retrieve a single webhook by id.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_webhooks_resource import V1WebhooksResource
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.WebhooksApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox.
    webhook = '019683f8-1234-7abc-8def-0123456789ab' # str | Webhook identifier (UUID v7).

    try:
        # Get webhook
        api_response = api_instance.get_webhook(mailbox_resource_id, webhook)
        print("The response of WebhooksApi->get_webhook:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling WebhooksApi->get_webhook: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox. | 
 **webhook** | **str**| Webhook identifier (UUID v7). | 

### Return type

[**V1WebhooksResource**](V1WebhooksResource.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Webhook payload. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_webhooks**
> V1WebhooksCollection list_webhooks(mailbox_resource_id, status=status, page=page, per_page=per_page)

List webhooks

List webhooks for a mailbox.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_webhooks_collection import V1WebhooksCollection
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.WebhooksApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    status = 'status_example' # str |  (optional)
    page = 1 # int |  (optional) (default to 1)
    per_page = 15 # int |  (optional) (default to 15)

    try:
        # List webhooks
        api_response = api_instance.list_webhooks(mailbox_resource_id, status=status, page=page, per_page=per_page)
        print("The response of WebhooksApi->list_webhooks:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling WebhooksApi->list_webhooks: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **status** | **str**|  | [optional] 
 **page** | **int**|  | [optional] [default to 1]
 **per_page** | **int**|  | [optional] [default to 15]

### Return type

[**V1WebhooksCollection**](V1WebhooksCollection.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Paginated list of webhooks. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **regenerate_webhook_secret**
> V1WebhooksResourceWithSecret regenerate_webhook_secret(mailbox_resource_id, webhook)

Regenerate webhook secret

Regenerate the webhook secret. The previous secret is immediately invalidated. The new secret is returned once.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_webhooks_resource_with_secret import V1WebhooksResourceWithSecret
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.WebhooksApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox.
    webhook = '019683f8-1234-7abc-8def-0123456789ab' # str | Webhook identifier (UUID v7).

    try:
        # Regenerate webhook secret
        api_response = api_instance.regenerate_webhook_secret(mailbox_resource_id, webhook)
        print("The response of WebhooksApi->regenerate_webhook_secret:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling WebhooksApi->regenerate_webhook_secret: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox. | 
 **webhook** | **str**| Webhook identifier (UUID v7). | 

### Return type

[**V1WebhooksResourceWithSecret**](V1WebhooksResourceWithSecret.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Webhook with new secret. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **test_webhook**
> V1WebhooksTestResult test_webhook(mailbox_resource_id, webhook)

Test webhook

Send a test delivery to the webhook URL and return the upstream response.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_webhooks_test_result import V1WebhooksTestResult
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.WebhooksApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox.
    webhook = '019683f8-1234-7abc-8def-0123456789ab' # str | Webhook identifier (UUID v7).

    try:
        # Test webhook
        api_response = api_instance.test_webhook(mailbox_resource_id, webhook)
        print("The response of WebhooksApi->test_webhook:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling WebhooksApi->test_webhook: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox. | 
 **webhook** | **str**| Webhook identifier (UUID v7). | 

### Return type

[**V1WebhooksTestResult**](V1WebhooksTestResult.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Test delivery result. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_webhook**
> V1WebhooksResource update_webhook(mailbox_resource_id, webhook, v1_webhooks_update_request)

Update webhook

Partially update a webhook.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_webhooks_resource import V1WebhooksResource
from hostinger_mail_api.models.v1_webhooks_update_request import V1WebhooksUpdateRequest
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.WebhooksApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox.
    webhook = '019683f8-1234-7abc-8def-0123456789ab' # str | Webhook identifier (UUID v7).
    v1_webhooks_update_request = hostinger_mail_api.V1WebhooksUpdateRequest() # V1WebhooksUpdateRequest | 

    try:
        # Update webhook
        api_response = api_instance.update_webhook(mailbox_resource_id, webhook, v1_webhooks_update_request)
        print("The response of WebhooksApi->update_webhook:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling WebhooksApi->update_webhook: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox. | 
 **webhook** | **str**| Webhook identifier (UUID v7). | 
 **v1_webhooks_update_request** | [**V1WebhooksUpdateRequest**](V1WebhooksUpdateRequest.md)|  | 

### Return type

[**V1WebhooksResource**](V1WebhooksResource.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Updated webhook. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

