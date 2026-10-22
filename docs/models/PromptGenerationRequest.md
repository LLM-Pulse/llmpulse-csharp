# LLMPulse.SDK.Model.PromptGenerationRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**Source** | **string** | Which Add prompts generator to run | 
**Query** | **string** | keyword: optional keyword or research query. topic and reddit: required topic (reddit: the brand when search_type&#x3D;brand). paa: one keyword, as an alternative to keywords. | [optional] 
**Count** | **int** | keyword and topic: how many suggestions to ask for, capped by the prompt slots left | [optional] [default to 20]
**CountryCode** | **string** | ISO 3166-1 alpha-2 country of the suggestions (default the project country) | [optional] 
**LanguageCode** | **string** | ISO language code of the suggestions (default the project language) | [optional] 
**CompetitorId** | **int** | keyword: write the suggestions around this competitor of the project | [optional] 
**SearchType** | **string** | reddit: search discussions of a topic or a brand | [optional] [default to SearchTypeEnum.Topic]
**Keywords** | **List&lt;string&gt;** | paa: up to 5 keywords; each is a People Also Ask lookup counted against the account&#39;s 24-hour allowance | [optional] 
**SourceCountryCode** | **string** | translate: country of the prompts to translate | [optional] 
**SourceLanguageCode** | **string** | translate: language of the prompts to translate | [optional] 
**MinWords** | **int** | search_console: skip queries shorter than this many words | [optional] [default to 0]
**AllCountries** | **bool** | search_console: include queries from every country instead of country_code only | [optional] [default to false]
**Property** | **string** | search_console: the property id to read queries from (GET /search_console/properties lists them); the primary property when omitted | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

