# V1QuotaResource

Mailbox quota payload.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**V1QuotaQuota**](V1QuotaQuota.md) |  | 

## Example

```python
from hostinger_mail_api.models.v1_quota_resource import V1QuotaResource

# TODO update the JSON string below
json = "{}"
# create an instance of V1QuotaResource from a JSON string
v1_quota_resource_instance = V1QuotaResource.from_json(json)
# print the JSON string representation of the object
print(V1QuotaResource.to_json())

# convert the object into a dict
v1_quota_resource_dict = v1_quota_resource_instance.to_dict()
# create an instance of V1QuotaResource from a dict
v1_quota_resource_from_dict = V1QuotaResource.from_dict(v1_quota_resource_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


