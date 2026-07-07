# V1WebhooksTestResultData


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**http_status** | **int** |  | 
**success** | **bool** |  | [optional] 
**error** | **str** |  | [optional] 

## Example

```python
from hostinger_email_api.models.v1_webhooks_test_result_data import V1WebhooksTestResultData

# TODO update the JSON string below
json = "{}"
# create an instance of V1WebhooksTestResultData from a JSON string
v1_webhooks_test_result_data_instance = V1WebhooksTestResultData.from_json(json)
# print the JSON string representation of the object
print(V1WebhooksTestResultData.to_json())

# convert the object into a dict
v1_webhooks_test_result_data_dict = v1_webhooks_test_result_data_instance.to_dict()
# create an instance of V1WebhooksTestResultData from a dict
v1_webhooks_test_result_data_from_dict = V1WebhooksTestResultData.from_dict(v1_webhooks_test_result_data_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


