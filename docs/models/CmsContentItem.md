# LLMPulse.SDK.Model.CmsContentItem

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** | WordPress post or page id | [optional] 
**Type** | **string** |  | [optional] 
**Status** | **string** | WordPress status (publish, future, draft, pending or private) | [optional] 
**Slug** | **string** |  | [optional] 
**Title** | **string** | Plain-text title as the site renders it | [optional] 
**Url** | **string** | The public link on the connected site; null when the site names a link on another host | [optional] 
**ModifiedAt** | **DateTime** |  | [optional] 
**Excerpt** | **string** | Plain-text excerpt, up to 2,000 characters | [optional] 
**ContentHtml** | **string** | Sanitized HTML (headings, paragraphs, lists, tables, quotes, code, links with href only), up to 200,000 characters | [optional] 
**ContentTruncated** | **bool** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

