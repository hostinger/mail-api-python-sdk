# hostinger_mail_api.AccountApi

All URIs are relative to *https://api.mail.hostinger.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_current_account**](AccountApi.md#get_current_account) | **GET** /api/v1/me | Get the authenticated account


# **get_current_account**
> V1MeResource get_current_account()

Get the authenticated account

Returns the authenticated account and the mailboxes it can manage.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_me_resource import V1MeResource
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.AccountApi(api_client)

    try:
        # Get the authenticated account
        api_response = api_instance.get_current_account()
        print("The response of AccountApi->get_current_account:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling AccountApi->get_current_account: %s\n" % e)
```



### Parameters

This endpoint does not need any parameter.

### Return type

[**V1MeResource**](V1MeResource.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Authenticated account with the mailboxes the API key can manage. |  -  |
**401** | Missing or invalid credentials. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

