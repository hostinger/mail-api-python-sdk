# hostinger_mail_api.SendApi

All URIs are relative to *https://api.mail.hostinger.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**send_email**](SendApi.md#send_email) | **POST** /api/v1/mailboxes/{mailboxResourceId}/send | Send email


# **send_email**
> send_email(mailbox_resource_id, v1_send_request)

Send email

Send a message from the managed mailbox. Saves a copy to INBOX.Sent.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_send_request import V1SendRequest
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.SendApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    v1_send_request = hostinger_mail_api.V1SendRequest() # V1SendRequest | 

    try:
        # Send email
        api_instance.send_email(mailbox_resource_id, v1_send_request)
    except Exception as e:
        print("Exception when calling SendApi->send_email: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **v1_send_request** | [**V1SendRequest**](V1SendRequest.md)|  | 

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
**204** | Message sent and saved to sent folder. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

