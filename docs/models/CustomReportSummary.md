# LLMPulse.SDK.Model.CustomReportSummary

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Id** | **int** |  | 
**Name** | **string** |  | 
**DateRange** | [**CustomReportDateRange**](CustomReportDateRange.md) |  | 
**Schedule** | [**CustomReportSchedule**](CustomReportSchedule.md) |  | 
**RecipientsCount** | **int** |  | 
**Published** | **bool** | Whether the shared link is published | 
**PublicLinkActive** | **bool** | Whether the shared link opens (published and not made inside a client portal) | 
**PasswordProtected** | **bool** |  | 
**PortalOnly** | **bool** | Made inside a client portal, so it cannot be shared or emailed | 
**WidgetCount** | **int** |  | 
**Widgets** | [**List&lt;CustomReportWidgetRef&gt;**](CustomReportWidgetRef.md) |  | 
**CreatedAt** | **DateTime** |  | 
**UpdatedAt** | **DateTime** |  | 
**LastSentAt** | **DateTime** | When the report was last emailed, on its schedule or with Send now | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

