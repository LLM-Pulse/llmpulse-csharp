# LLMPulse.SDK.Model.AiModelPositionDistributionBrand

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Type** | **string** | project or competitor | 
**Id** | **int** | Project id, or competitor id | 
**Name** | **string** |  | 
**Buckets** | [**List&lt;AiModelPositionDistributionBrandBucketsInner&gt;**](AiModelPositionDistributionBrandBucketsInner.md) | One per position bucket, in order: position_1, position_2_3, position_4_7 and position_8_plus | 
**MaxStackedValue** | **int** | The brand&#39;s largest mentions count of one period, its buckets added up | 
**CompetitorId** | **int** | Null for the project, the competitor id otherwise | 
**Domain** | **string** | Bare (scheme-less) domain. Null for the project when it has no URL. | 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

