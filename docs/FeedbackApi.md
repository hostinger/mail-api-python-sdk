# hostinger_mail_api.FeedbackApi

All URIs are relative to *https://api.mail.hostinger.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**submit_feedback**](FeedbackApi.md#submit_feedback) | **POST** /api/v1/mailboxes/{mailboxResourceId}/feedback | Submit feedback


# **submit_feedback**
> submit_feedback(mailbox_resource_id, v1_feedback_submit_request)

Submit feedback

Report a problem or suggestion about this API or the MCP server to the Hostinger mail team.

Report when a call returned 4xx/5xx or unexpected data, was too slow, when documentation was missing or unclear, or when a capability you needed does not exist. Mention the failing operation and the status code you received so the team can find the request. Never include tokens, passwords or email contents: the message is scrubbed of secrets and capped at 2000 characters. Send one report per distinct issue.

A `429` (`ERR_FEEDBACK_RATE_LIMIT`) means feedback for this customer was submitted less than ten seconds ago; wait and retry.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_feedback_submit_request import V1FeedbackSubmitRequest
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.FeedbackApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the feedback is about, as returned by `GET /api/v1/me`.
    v1_feedback_submit_request = hostinger_mail_api.V1FeedbackSubmitRequest() # V1FeedbackSubmitRequest | 

    try:
        # Submit feedback
        api_instance.submit_feedback(mailbox_resource_id, v1_feedback_submit_request)
    except Exception as e:
        print("Exception when calling FeedbackApi->submit_feedback: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the feedback is about, as returned by &#x60;GET /api/v1/me&#x60;. | 
 **v1_feedback_submit_request** | [**V1FeedbackSubmitRequest**](V1FeedbackSubmitRequest.md)|  | 

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
**204** | Feedback accepted. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**429** | Feedback for this customer was submitted less than ten seconds ago. Wait and retry. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |
**504** | Upstream service did not respond within the configured timeout. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

