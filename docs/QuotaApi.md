# hostinger_email_api.QuotaApi

All URIs are relative to *https://api.mail.hostinger.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_quota**](QuotaApi.md#get_quota) | **GET** /api/v1/mailboxes/{mailboxResourceId}/quota | Get mailbox quota


# **get_quota**
> V1QuotaResource get_quota(mailbox_resource_id)

Get mailbox quota

Retrieve storage and message quota usage for the managed mailbox.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_email_api
from hostinger_email_api.models.v1_quota_resource import V1QuotaResource
from hostinger_email_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_email_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_email_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_email_api.QuotaApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.

    try:
        # Get mailbox quota
        api_response = api_instance.get_quota(mailbox_resource_id)
        print("The response of QuotaApi->get_quota:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling QuotaApi->get_quota: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 

### Return type

[**V1QuotaResource**](V1QuotaResource.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Mailbox quota usage. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

