# hostinger_mail_api.CalendarsApi

All URIs are relative to *https://api.mail.hostinger.com*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_calendar**](CalendarsApi.md#create_calendar) | **POST** /api/v1/mailboxes/{mailboxResourceId}/calendars | Create calendar
[**delete_calendar**](CalendarsApi.md#delete_calendar) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid} | Delete calendar
[**get_calendar**](CalendarsApi.md#get_calendar) | **GET** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid} | Get calendar
[**list_calendars**](CalendarsApi.md#list_calendars) | **GET** /api/v1/mailboxes/{mailboxResourceId}/calendars | List calendars
[**update_calendar**](CalendarsApi.md#update_calendar) | **PUT** /api/v1/mailboxes/{mailboxResourceId}/calendars/{calendarUuid} | Update calendar


# **create_calendar**
> V1CalendarsResource create_calendar(mailbox_resource_id, v1_calendars_create_request)

Create calendar

Create a calendar owned by the mailbox. The number of calendars a mailbox can own is limited; when the limit is reached the request fails with `400` and code `ERR_CALENDAR_LIMIT_REACHED`.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_calendars_create_request import V1CalendarsCreateRequest
from hostinger_mail_api.models.v1_calendars_resource import V1CalendarsResource
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.CalendarsApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    v1_calendars_create_request = hostinger_mail_api.V1CalendarsCreateRequest() # V1CalendarsCreateRequest | 

    try:
        # Create calendar
        api_response = api_instance.create_calendar(mailbox_resource_id, v1_calendars_create_request)
        print("The response of CalendarsApi->create_calendar:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling CalendarsApi->create_calendar: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **v1_calendars_create_request** | [**V1CalendarsCreateRequest**](V1CalendarsCreateRequest.md)|  | 

### Return type

[**V1CalendarsResource**](V1CalendarsResource.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**201** | Calendar created. |  -  |
**400** | The mailbox already owns as many calendars as allowed. Calendars shared with the mailbox are not counted. &#x60;params.maxCalendars&#x60; holds the limit. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **delete_calendar**
> delete_calendar(mailbox_resource_id, calendar_uuid)

Delete calendar

Delete a calendar owned by the mailbox together with all its events, or remove a calendar shared with the mailbox from its list. This cannot be undone. A calendar that cannot be deleted is rejected with `403` and code `ERR_CALENDAR_NOT_DELETABLE`.

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
    api_instance = hostinger_mail_api.CalendarsApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    calendar_uuid = '42c370e3-48ae-4286-90c5-d952f28c67cc' # str | Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`.

    try:
        # Delete calendar
        api_instance.delete_calendar(mailbox_resource_id, calendar_uuid)
    except Exception as e:
        print("Exception when calling CalendarsApi->delete_calendar: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **calendar_uuid** | **str**| Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | 

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
**204** | Calendar deleted. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **get_calendar**
> V1CalendarsResource get_calendar(mailbox_resource_id, calendar_uuid)

Get calendar

Retrieve one calendar of a mailbox: its name, description, color, whether it is the default calendar and whether it is shown in the calendar view. It does not return events; use `listCalendarEvents` for those.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_calendars_resource import V1CalendarsResource
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.CalendarsApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    calendar_uuid = '42c370e3-48ae-4286-90c5-d952f28c67cc' # str | Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`.

    try:
        # Get calendar
        api_response = api_instance.get_calendar(mailbox_resource_id, calendar_uuid)
        print("The response of CalendarsApi->get_calendar:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling CalendarsApi->get_calendar: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **calendar_uuid** | **str**| Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | 

### Return type

[**V1CalendarsResource**](V1CalendarsResource.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Calendar payload. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **list_calendars**
> V1CalendarsCollection list_calendars(mailbox_resource_id, page=page, per_page=per_page)

List calendars

List the calendars of a mailbox: its own calendars and the calendars shared with it, in display order. Call it first to get the `calendarUuid` every calendar event operation needs: the `uuid` of each calendar. The calendar with `default` true is where new events go unless another one is named. `visible` false means the calendar is hidden in the calendar view; its events still exist.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_calendars_collection import V1CalendarsCollection
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.CalendarsApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    page = 1 # int | Page number (1-based). (optional) (default to 1)
    per_page = 25 # int | Items per page (max 200). (optional) (default to 25)

    try:
        # List calendars
        api_response = api_instance.list_calendars(mailbox_resource_id, page=page, per_page=per_page)
        print("The response of CalendarsApi->list_calendars:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling CalendarsApi->list_calendars: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **page** | **int**| Page number (1-based). | [optional] [default to 1]
 **per_page** | **int**| Items per page (max 200). | [optional] [default to 25]

### Return type

[**V1CalendarsCollection**](V1CalendarsCollection.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Paginated list of calendars. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

# **update_calendar**
> V1CalendarsResource update_calendar(mailbox_resource_id, calendar_uuid, v1_calendars_update_request)

Update calendar

Update the name, description, color and visibility of a calendar. Name, description and color replace the stored values: an omitted `description` is cleared and an omitted `color` resets to the default color. An omitted `visible` keeps the current value.

### Example

* Bearer Authentication (BearerAuth):

```python
import hostinger_mail_api
from hostinger_mail_api.models.v1_calendars_resource import V1CalendarsResource
from hostinger_mail_api.models.v1_calendars_update_request import V1CalendarsUpdateRequest
from hostinger_mail_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_mail_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)

# Enter a context with an instance of the API client
with hostinger_mail_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_mail_api.CalendarsApi(api_client)
    mailbox_resource_id = 'AC1a2b3c4d5e6f7g' # str | Resource ID of the managed mailbox the bearer token is authorized for.
    calendar_uuid = '42c370e3-48ae-4286-90c5-d952f28c67cc' # str | Calendar identifier: the `uuid` of a calendar returned by `listCalendars`, or the `calendarUuid` of an event returned by `listCalendarEvents`.
    v1_calendars_update_request = hostinger_mail_api.V1CalendarsUpdateRequest() # V1CalendarsUpdateRequest | 

    try:
        # Update calendar
        api_response = api_instance.update_calendar(mailbox_resource_id, calendar_uuid, v1_calendars_update_request)
        print("The response of CalendarsApi->update_calendar:\n")
        pprint(api_response)
    except Exception as e:
        print("Exception when calling CalendarsApi->update_calendar: %s\n" % e)
```



### Parameters


Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **mailbox_resource_id** | **str**| Resource ID of the managed mailbox the bearer token is authorized for. | 
 **calendar_uuid** | **str**| Calendar identifier: the &#x60;uuid&#x60; of a calendar returned by &#x60;listCalendars&#x60;, or the &#x60;calendarUuid&#x60; of an event returned by &#x60;listCalendarEvents&#x60;. | 
 **v1_calendars_update_request** | [**V1CalendarsUpdateRequest**](V1CalendarsUpdateRequest.md)|  | 

### Return type

[**V1CalendarsResource**](V1CalendarsResource.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json

### HTTP response details

| Status code | Description | Response headers |
|-------------|-------------|------------------|
**200** | Updated calendar. |  -  |
**401** | Missing or invalid credentials. |  -  |
**403** | Token is not authorized to manage the requested mailbox. |  -  |
**404** | Resource not found. |  -  |
**422** | Request payload failed validation. &#x60;params&#x60; maps field name to an array of error messages. |  -  |
**500** | Server-side failure. |  -  |
**502** | Upstream service is unavailable or returned an unexpected response. |  -  |

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)

