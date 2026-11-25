# LLMPulse.SDK.Model.OwnedMediaKpis

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Total** | **int** | Citations of the platform in the window, yours and everyone else&#39;s | [optional] 
**Yours** | **int** | Citations of your own profiles and their content | [optional] 
**YourProfile** | **int** | Citations of your profile or channel pages. Null for mobile_apps and overview | [optional] 
**YourContent** | **int** | Citations of your posts or videos. Null for mobile_apps and overview | [optional] 
**SharePct** | **decimal** | yours as a percentage of total (0-100) | [optional] 
**UniqueSubreddits** | **int** | Number of cited subreddits (provider&#x3D;reddit; null or omitted for other providers) | [optional] 
**UniqueAuthors** | **int** | Number of cited Reddit authors (provider&#x3D;reddit; null or omitted for other providers) | [optional] 
**PositivePct** | **decimal** | Positive sentiment among rated Reddit citations, as a percentage (provider&#x3D;reddit; null or omitted for other providers) | [optional] 
**ConnectedCount** | **int** | provider&#x3D;overview only. The platforms with a connected profile, channel or app, out of the rows in platforms (the Connected sources card). It describes the current setup, so previous.kpis and changes leave it out | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

