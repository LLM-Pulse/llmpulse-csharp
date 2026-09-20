# LLMPulse.SDK.Model.CreateCompetitorRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**BrandName** | **string** |  | 
**Domain** | **string** | URL is accepted and normalised to host (e.g. https://www.openai.com → openai.com) | 
**MatchingNames** | **List&lt;string&gt;** |  | [optional] 
**CitationMatchMode** | **string** | domain includes the registrable domain and all subdomains; host requires the exact hostname; path_prefix also requires citation_match_path | [optional] [default to CitationMatchModeEnum.Domain]
**CitationMatchPath** | **string** | Required when citation_match_mode&#x3D;path_prefix, e.g. /es. Case-sensitive; trailing slash is optional; query and fragment are ignored | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

