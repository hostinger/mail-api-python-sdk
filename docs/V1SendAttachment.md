# V1SendAttachment

Attachment payload for outgoing mail. Supports regular attachments and inline images linked via Content-ID.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**filename** | **str** |  | 
**content** | **str** | Attachment body. Base64-encoded by default; set encoding to switch. | 
**content_type** | **str** |  | [optional] 
**cid** | **str** | Content-ID for inline images. Reference from HTML as &lt;img src&#x3D;\&quot;cid:logo\&quot;&gt;. | [optional] 
**encoding** | **str** | Encoding of content. Defaults to base64. | [optional] 

## Example

```python
from hostinger_email_api.models.v1_send_attachment import V1SendAttachment

# TODO update the JSON string below
json = "{}"
# create an instance of V1SendAttachment from a JSON string
v1_send_attachment_instance = V1SendAttachment.from_json(json)
# print the JSON string representation of the object
print(V1SendAttachment.to_json())

# convert the object into a dict
v1_send_attachment_dict = v1_send_attachment_instance.to_dict()
# create an instance of V1SendAttachment from a dict
v1_send_attachment_from_dict = V1SendAttachment.from_dict(v1_send_attachment_dict)
```
[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


