# V1QuotaQuota

Storage and message quota usage for the managed mailbox.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**quotas** | [**List[V1QuotaQuotaResource]**](V1QuotaQuotaResource.md) | Per-resource quota breakdown reported by the IMAP server. | 
**total_usage** | **int** | Aggregate storage usage across all resources, in bytes. | 
**total_limit** | **int** | Aggregate storage limit across all resources, in bytes. | 
**total_percentage** | **int** | Aggregate storage usage as a percentage of the total limit. | 
**supported** | **bool** | Whether the IMAP server reports quota information for this mailbox. | 

## Example

```python
from hostinger_mail_api.models.v1_quota_quota import V1QuotaQuota

# TODO update the JSON string below
json = "{}"
# create an instance of V1QuotaQuota from a JSON string
v1_quota_quota_instance = V1QuotaQuota.from_json(json)
# print the JSON string representation of the object
print(V1QuotaQuota.to_json())

# convert the object into a dict
v1_quota_quota_dict = v1_quota_quota_instance.to_dict()
# create an instance of V1QuotaQuota from a dict
v1_quota_quota_from_dict = V1QuotaQuota.from_dict(v1_quota_quota_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


