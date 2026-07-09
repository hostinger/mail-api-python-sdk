# V1WebhooksTestResult

Result of a webhook test delivery.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**V1WebhooksTestResultData**](V1WebhooksTestResultData.md) |  | 

## Example

```python
from hostinger_mail_api.models.v1_webhooks_test_result import V1WebhooksTestResult

# TODO update the JSON string below
json = "{}"
# create an instance of V1WebhooksTestResult from a JSON string
v1_webhooks_test_result_instance = V1WebhooksTestResult.from_json(json)
# print the JSON string representation of the object
print(V1WebhooksTestResult.to_json())

# convert the object into a dict
v1_webhooks_test_result_dict = v1_webhooks_test_result_instance.to_dict()
# create an instance of V1WebhooksTestResult from a dict
v1_webhooks_test_result_from_dict = V1WebhooksTestResult.from_dict(v1_webhooks_test_result_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


