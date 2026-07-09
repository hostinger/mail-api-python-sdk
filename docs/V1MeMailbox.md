# V1MeMailbox

A mailbox the authenticated API token can manage.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**resource_id** | **str** | Unique identifier of the mailbox. | 
**address** | **str** | Email address of the mailbox. | 

## Example

```python
from hostinger_mail_api.models.v1_me_mailbox import V1MeMailbox

# TODO update the JSON string below
json = "{}"
# create an instance of V1MeMailbox from a JSON string
v1_me_mailbox_instance = V1MeMailbox.from_json(json)
# print the JSON string representation of the object
print(V1MeMailbox.to_json())

# convert the object into a dict
v1_me_mailbox_dict = v1_me_mailbox_instance.to_dict()
# create an instance of V1MeMailbox from a dict
v1_me_mailbox_from_dict = V1MeMailbox.from_dict(v1_me_mailbox_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


