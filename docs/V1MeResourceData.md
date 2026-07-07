# V1MeResourceData


## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**order_resource_id** | **str** | Identifier of the order this API token is scoped to. | 
**mailboxes** | [**List[V1MeMailbox]**](V1MeMailbox.md) | Mailboxes that the authenticated API token can manage. | 

## Example

```python
from hostinger_email_api.models.v1_me_resource_data import V1MeResourceData

# TODO update the JSON string below
json = "{}"
# create an instance of V1MeResourceData from a JSON string
v1_me_resource_data_instance = V1MeResourceData.from_json(json)
# print the JSON string representation of the object
print(V1MeResourceData.to_json())

# convert the object into a dict
v1_me_resource_data_dict = v1_me_resource_data_instance.to_dict()
# create an instance of V1MeResourceData from a dict
v1_me_resource_data_from_dict = V1MeResourceData.from_dict(v1_me_resource_data_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


