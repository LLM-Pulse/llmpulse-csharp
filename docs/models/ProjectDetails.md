# LLMPulse.SDK.Model.ProjectDetails

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Tracked** | **bool** | Whether scheduled runs include this project. False when it is a pitch project, which runs once, when it is paused, or when the plan&#39;s project limit leaves it out (the oldest projects up to the limit run), so its prompts do not run | 
**Id** | **int** |  | [optional] 
**Name** | **string** | Internal project label (sidebar, settings, admin) | [optional] 
**BrandName** | **string** | LLM-facing brand label (used in prompts and customer-facing charts). Null when not set, in which case prompts and charts use &#x60;name&#x60;. | [optional] 
**UntrackedReason** | **string** | Why tracked is false: pitch_project, paused or project_limit. Null when tracked | 
**Pitch** | **bool** | Whether this is a pitch project, a one-off snapshot that runs its prompts once, takes no project slot and is deleted at pitch_expires_at unless it is converted (PATCH /projects/{id} with pitch false) | [optional] 
**PitchExpiresAt** | **DateTime** | When a pitch project is deleted, with its data, unless it is converted first. Null for a tracked project | [optional] 
**Url** | **string** |  | [optional] 
**Description** | **string** |  | [optional] 
**MatchingNames** | **List&lt;string&gt;** |  | [optional] 
**AdditionalOwnedDomains** | **List&lt;string&gt;** | Other domains the brand owns (at most 10, each a website&#39;s own domain covering its subdomains), whose citations count as owned like the project website. Empty when none | [optional] 
**Industry** | **Object** | Industry as stored: one key as a string (e.g. SAAS), or an array of key strings when the project was created with a list or the in-app multi-select. Deliberately untyped so generated clients decode either shape | [optional] 
**BusinessModel** | **string** |  | [optional] 
**BusinessModelOther** | **string** | Set only when business_model is OTHER | [optional] 
**PrimaryProducts** | **List&lt;string&gt;** |  | [optional] 
**TargetAudience** | **string** |  | [optional] 
**BrandVoice** | **string** |  | [optional] 
**Goals** | **string** |  | [optional] 
**CountryCode** | **string** |  | [optional] 
**LanguageCode** | **string** |  | [optional] 
**Paused** | **bool** |  | [optional] 
**GooglePlayId** | **string** |  | [optional] 
**AppStoreId** | **string** |  | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**PromptLimit** | **int** | The most prompts this project can hold, set by the account owner or a co-owner (Account Settings &gt; Prompt Limits). Null when the project has no limit of its own; the account&#39;s plan allowance applies either way | [optional] 
**ProjectType** | **string** | The project type it is billed as under the account&#39;s pricing agreement, such as core or lean (its own, else the account&#39;s default type). Null for accounts without per-project types and for pitch projects | [optional] 
**Stats** | [**ProjectDetailsAllOfStats**](ProjectDetailsAllOfStats.md) |  | [optional] 
**PitchRun** | [**ProjectDetailsAllOfPitchRun**](ProjectDetailsAllOfPitchRun.md) |  | [optional] 
**DataCoverage** | [**ProjectDetailsAllOfDataCoverage**](ProjectDetailsAllOfDataCoverage.md) |  | [optional] 
**SearchConsole** | [**ProjectDetailsAllOfSearchConsole**](ProjectDetailsAllOfSearchConsole.md) |  | [optional] 
**AiTraffic** | [**ProjectDetailsAllOfAiTraffic**](ProjectDetailsAllOfAiTraffic.md) |  | [optional] 
**AgentTraffic** | [**ProjectDetailsAllOfAgentTraffic**](ProjectDetailsAllOfAgentTraffic.md) |  | [optional] 
**RequestId** | **string** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

