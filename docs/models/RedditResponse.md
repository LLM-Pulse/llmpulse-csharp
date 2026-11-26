# LLMPulse.SDK.Model.RedditResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**Page** | **int** |  | 
**PerPage** | **int** |  | 
**Total** | **int** | Rows matching the filters across every page | 
**RequestId** | **string** |  | 
**View** | **string** | subreddits, authors, threads or breakdowns | 
**From** | **DateTime** | Start of the window, 30 days back by default | 
**To** | **DateTime** |  | 
**Data** | [**List&lt;RedditRow&gt;**](RedditRow.md) |  | 
**Citations** | **int** | Reddit citations after the filters (view&#x3D;breakdowns) | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

