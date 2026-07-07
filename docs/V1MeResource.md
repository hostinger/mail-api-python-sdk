# V1MeResource

Authenticated account payload.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | [**V1MeResourceData**](V1MeResourceData.md) |  | 

## Example

```python
from hostinger_email_api.models.v1_me_resource import V1MeResource

# TODO update the JSON string below
json = "{}"
# create an instance of V1MeResource from a JSON string
v1_me_resource_instance = V1MeResource.from_json(json)
# print the JSON string representation of the object
print(V1MeResource.to_json())

# convert the object into a dict
v1_me_resource_dict = v1_me_resource_instance.to_dict()
# create an instance of V1MeResource from a dict
v1_me_resource_from_dict = V1MeResource.from_dict(v1_me_resource_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


