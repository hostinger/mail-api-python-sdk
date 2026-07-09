# V1QuotaQuotaResource

Usage and limit for a single IMAP quota resource.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**resource_name** | **str** | Name of the quota resource as reported by the IMAP server. | 
**usage** | **int** | Current usage of the resource (bytes for STORAGE, count for MESSAGE). | 
**limit** | **int** | Maximum allowed value for the resource (bytes for STORAGE, count for MESSAGE). | 
**percentage** | **int** | Usage as a percentage of the limit. | 

## Example

```python
from hostinger_mail_api.models.v1_quota_quota_resource import V1QuotaQuotaResource

# TODO update the JSON string below
json = "{}"
# create an instance of V1QuotaQuotaResource from a JSON string
v1_quota_quota_resource_instance = V1QuotaQuotaResource.from_json(json)
# print the JSON string representation of the object
print(V1QuotaQuotaResource.to_json())

# convert the object into a dict
v1_quota_quota_resource_dict = v1_quota_quota_resource_instance.to_dict()
# create an instance of V1QuotaQuotaResource from a dict
v1_quota_quota_resource_from_dict = V1QuotaQuotaResource.from_dict(v1_quota_quota_resource_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


