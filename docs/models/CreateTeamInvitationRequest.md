# LLMPulse.SDK.Model.CreateTeamInvitationRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Email** | **string** |  | 
**ProjectIds** | **List&lt;int&gt;** | Projects the member can access. Send this or all_projects true. | [optional] 
**AllProjects** | **bool** | Access to every project, including future ones | [optional] 
**PermissionRole** | **string** | Default full_access. Owner and co-owners only. | [optional] 
**AccountRoleId** | **int** | One of the account&#39;s roles, with permission_role account_role | [optional] 
**Permissions** | **Dictionary&lt;string, List&lt;string&gt;&gt;** | With permission_role custom: feature key to the verbs granted (read, create, update, delete), for example {\&quot;overview\&quot;: [\&quot;read\&quot;], \&quot;prompts\&quot;: [\&quot;read\&quot;, \&quot;create\&quot;]} | [optional] 
**AccountAdmin** | **bool** | Make the member a co-owner. Account owner only. | [optional] 
**BillingAccess** | **bool** | Access to Billing and Plans. Account owner only. | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

