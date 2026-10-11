# LLMPulse.SDK.Model.TeamMember

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | 
**Email** | **string** |  | 
**Role** | **string** | The account owner is listed first; everyone else who joined is a member. | 
**Status** | **string** | A blocked member cannot sign in or use the API until unblocked in the app. | 
**AccountAdmin** | **bool** | A co-owner, who can manage the team. | 
**BillingAccess** | **bool** | Can open Billing and Plans (always true for the owner). | 
**AllProjects** | **bool** | Has access to every project of the account, including future ones. | 
**ProjectIds** | **List&lt;int&gt;** | The projects a member is limited to; empty when all_projects is true. | 
**Name** | **string** |  | [optional] 
**PermissionRole** | **string** | Access level of a member: full_access, view_only, custom or account_role. Null for the owner. | 
**AccountRole** | [**TeamAccountRole**](TeamAccountRole.md) |  | 
**Permissions** | **Dictionary&lt;string, List&lt;string&gt;&gt;** | What the person can do, feature key to the verbs granted (read, create, update, delete), resolved from their role. Null for the account owner, who can do everything. | 
**LastSignInAt** | **DateTime** |  | [optional] 
**JoinedAt** | **DateTime** | When the member accepted the invitation; null for the owner and for members added without one. | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

