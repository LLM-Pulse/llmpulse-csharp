# LLMPulse.SDK.Model.TeamInvitation

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** | Kept by the member once they accept, when they move to GET /team_members. | 
**Email** | **string** |  | 
**PermissionRole** | **string** |  | 
**AccountAdmin** | **bool** |  | 
**BillingAccess** | **bool** |  | 
**AllProjects** | **bool** |  | 
**ProjectIds** | **List&lt;int&gt;** |  | 
**AccountRole** | [**TeamAccountRole**](TeamAccountRole.md) |  | 
**Permissions** | **Dictionary&lt;string, List&lt;string&gt;&gt;** | What the person can do, feature key to the verbs granted (read, create, update, delete), resolved from their role. Null for the account owner, who can do everything. | 
**InvitedAt** | **DateTime** | When the invitation email was last sent. | [optional] 
**ExpiresAt** | **DateTime** | When the invitation link stops working. | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

