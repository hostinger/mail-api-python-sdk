# Hostinger Email API Python SDK

[![PyPI version](https://badge.fury.io/py/hostinger_email_api.svg)](https://badge.fury.io/py/hostinger_email_api)

## About
This is a Python SDK for the [Hostinger API](https://developers.hostinger.com).


## Requirements.

Python 3.9+

## Installation & Usage
### pip install

Setup new virtual environment (optional but recommended):
```sh
python3 -m venv venv
source venv/bin/activate
```

Install the package via [pip](https://pypi.org/project/pip/):
```sh
pip install hostinger_email_api
```

Then import the package:
```python
import hostinger_email_api
```

### Setuptools

Install via [Setuptools](http://pypi.python.org/pypi/setuptools).

```sh
python setup.py install --user
```
(or `sudo python setup.py install` to install the package for all users)

Then import the package:
```python
import hostinger_email_api
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```python

import hostinger_email_api
from hostinger_email_api.rest import ApiException
from pprint import pprint


# Configure Bearer authorization: BearerAuth
configuration = hostinger_email_api.Configuration(
    access_token = os.environ["BEARER_TOKEN"]
)


# Enter a context with an instance of the API client
with hostinger_email_api.ApiClient(configuration) as api_client:
    # Create an instance of the API class
    api_instance = hostinger_email_api.AccountApi(api_client)

    try:
        # Get the authenticated account
        api_response = api_instance.get_current_account()
        print("The response of AccountApi->get_current_account:\n")
        pprint(api_response)
    except ApiException as e:
        print("Exception when calling AccountApi->get_current_account: %s\n" % e)

```

## Documentation for API Endpoints

All URIs are relative to *https://api.mail.hostinger.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AccountApi* | [**get_current_account**](docs/AccountApi.md#get_current_account) | **GET** /api/v1/me | Get the authenticated account
*FoldersApi* | [**create_folder**](docs/FoldersApi.md#create_folder) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders | Create folder
*FoldersApi* | [**delete_folder**](docs/FoldersApi.md#delete_folder) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder} | Delete folder
*FoldersApi* | [**list_folders**](docs/FoldersApi.md#list_folders) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders | List folders
*FoldersApi* | [**update_folder**](docs/FoldersApi.md#update_folder) | **PUT** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder} | Update folder
*MessagesApi* | [**delete_all_messages**](docs/MessagesApi.md#delete_all_messages) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages | Delete all messages
*MessagesApi* | [**delete_message**](docs/MessagesApi.md#delete_message) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid} | Delete message
*MessagesApi* | [**delete_messages**](docs/MessagesApi.md#delete_messages) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/delete | Delete messages
*MessagesApi* | [**get_message**](docs/MessagesApi.md#get_message) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid} | Get message
*MessagesApi* | [**get_message_attachment**](docs/MessagesApi.md#get_message_attachment) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid}/attachments/{attachmentId} | Download message attachment
*MessagesApi* | [**get_message_source**](docs/MessagesApi.md#get_message_source) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid}/source | Get message source
*MessagesApi* | [**get_message_text**](docs/MessagesApi.md#get_message_text) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid}/text | Get message text content
*MessagesApi* | [**list_messages**](docs/MessagesApi.md#list_messages) | **GET** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages | List messages
*MessagesApi* | [**move_message**](docs/MessagesApi.md#move_message) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid}/move | Move message
*MessagesApi* | [**move_messages**](docs/MessagesApi.md#move_messages) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/move | Move messages
*MessagesApi* | [**patch_message**](docs/MessagesApi.md#patch_message) | **PATCH** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/{uid} | Update message flags
*MessagesApi* | [**search_messages**](docs/MessagesApi.md#search_messages) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/search | Search messages
*MessagesApi* | [**update_message_flags**](docs/MessagesApi.md#update_message_flags) | **POST** /api/v1/mailboxes/{mailboxResourceId}/folders/{folder}/messages/flags | Update message flags
*QuotaApi* | [**get_quota**](docs/QuotaApi.md#get_quota) | **GET** /api/v1/mailboxes/{mailboxResourceId}/quota | Get mailbox quota
*SendApi* | [**send_email**](docs/SendApi.md#send_email) | **POST** /api/v1/mailboxes/{mailboxResourceId}/send | Send email
*WebhooksApi* | [**create_webhook**](docs/WebhooksApi.md#create_webhook) | **POST** /api/v1/mailboxes/{mailboxResourceId}/webhooks | Create webhook
*WebhooksApi* | [**delete_webhook**](docs/WebhooksApi.md#delete_webhook) | **DELETE** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook} | Delete webhook
*WebhooksApi* | [**get_webhook**](docs/WebhooksApi.md#get_webhook) | **GET** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook} | Get webhook
*WebhooksApi* | [**list_webhooks**](docs/WebhooksApi.md#list_webhooks) | **GET** /api/v1/mailboxes/{mailboxResourceId}/webhooks | List webhooks
*WebhooksApi* | [**regenerate_webhook_secret**](docs/WebhooksApi.md#regenerate_webhook_secret) | **POST** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook}/regenerate-secret | Regenerate webhook secret
*WebhooksApi* | [**test_webhook**](docs/WebhooksApi.md#test_webhook) | **POST** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook}/test | Test webhook
*WebhooksApi* | [**update_webhook**](docs/WebhooksApi.md#update_webhook) | **PATCH** /api/v1/mailboxes/{mailboxResourceId}/webhooks/{webhook} | Update webhook


## Documentation For Models

 - [Error](docs/Error.md)
 - [Pagination](docs/Pagination.md)
 - [V1FolderMessagesCollection](docs/V1FolderMessagesCollection.md)
 - [V1FolderMessagesDeleteBulkRequest](docs/V1FolderMessagesDeleteBulkRequest.md)
 - [V1FolderMessagesFlagsBulkRequest](docs/V1FolderMessagesFlagsBulkRequest.md)
 - [V1FolderMessagesFlagsRequest](docs/V1FolderMessagesFlagsRequest.md)
 - [V1FolderMessagesMessage](docs/V1FolderMessagesMessage.md)
 - [V1FolderMessagesMessageAddress](docs/V1FolderMessagesMessageAddress.md)
 - [V1FolderMessagesMessageAttachment](docs/V1FolderMessagesMessageAttachment.md)
 - [V1FolderMessagesMessageText](docs/V1FolderMessagesMessageText.md)
 - [V1FolderMessagesMessageTextResource](docs/V1FolderMessagesMessageTextResource.md)
 - [V1FolderMessagesMoveBulkRequest](docs/V1FolderMessagesMoveBulkRequest.md)
 - [V1FolderMessagesMoveRequest](docs/V1FolderMessagesMoveRequest.md)
 - [V1FolderMessagesResource](docs/V1FolderMessagesResource.md)
 - [V1FolderMessagesSearchRequest](docs/V1FolderMessagesSearchRequest.md)
 - [V1FolderMessagesUpdateFlagsResult](docs/V1FolderMessagesUpdateFlagsResult.md)
 - [V1FolderMessagesUpdateFlagsResultData](docs/V1FolderMessagesUpdateFlagsResultData.md)
 - [V1FolderMessagesUpdateFlagsResultDataFailedInner](docs/V1FolderMessagesUpdateFlagsResultDataFailedInner.md)
 - [V1FoldersCollection](docs/V1FoldersCollection.md)
 - [V1FoldersCreateRequest](docs/V1FoldersCreateRequest.md)
 - [V1FoldersFolder](docs/V1FoldersFolder.md)
 - [V1FoldersResource](docs/V1FoldersResource.md)
 - [V1FoldersUpdateRequest](docs/V1FoldersUpdateRequest.md)
 - [V1MeMailbox](docs/V1MeMailbox.md)
 - [V1MeResource](docs/V1MeResource.md)
 - [V1MeResourceData](docs/V1MeResourceData.md)
 - [V1QuotaQuota](docs/V1QuotaQuota.md)
 - [V1QuotaQuotaResource](docs/V1QuotaQuotaResource.md)
 - [V1QuotaResource](docs/V1QuotaResource.md)
 - [V1SendAttachment](docs/V1SendAttachment.md)
 - [V1SendRequest](docs/V1SendRequest.md)
 - [V1WebhooksCollection](docs/V1WebhooksCollection.md)
 - [V1WebhooksCreateRequest](docs/V1WebhooksCreateRequest.md)
 - [V1WebhooksResource](docs/V1WebhooksResource.md)
 - [V1WebhooksResourceWithSecret](docs/V1WebhooksResourceWithSecret.md)
 - [V1WebhooksTestResult](docs/V1WebhooksTestResult.md)
 - [V1WebhooksTestResultData](docs/V1WebhooksTestResultData.md)
 - [V1WebhooksUpdateRequest](docs/V1WebhooksUpdateRequest.md)
 - [V1WebhooksWebhook](docs/V1WebhooksWebhook.md)
 - [V1WebhooksWebhookWithSecret](docs/V1WebhooksWebhookWithSecret.md)


