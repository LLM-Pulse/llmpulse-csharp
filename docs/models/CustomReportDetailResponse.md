# LLMPulse.SDK.Model.CustomReportDetailResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ProjectId** | **int** |  | 
**Id** | **int** |  | 
**Name** | **string** |  | 
**DateRange** | [**CustomReportDateRange**](CustomReportDateRange.md) |  | 
**Schedule** | [**CustomReportSchedule**](CustomReportSchedule.md) |  | 
**Filters** | [**CustomReportFilters**](CustomReportFilters.md) |  | 
**GeneratedAt** | **DateTime** |  | 
**Blocks** | [**List&lt;CustomReportBlock&gt;**](CustomReportBlock.md) | The report layout in order | 
**Widgets** | [**List&lt;CustomReportWidget&gt;**](CustomReportWidget.md) |  | 
**RequestId** | **string** |  | 
**RecipientsCount** | **int** |  | [optional] 
**Published** | **bool** |  | [optional] 
**PublicLinkActive** | **bool** |  | [optional] 
**PasswordProtected** | **bool** |  | [optional] 
**PortalOnly** | **bool** |  | [optional] 
**LastSentAt** | **DateTime** | When the report was last emailed, on its schedule or with Send now | [optional] 
**CreatedAt** | **DateTime** |  | [optional] 
**UpdatedAt** | **DateTime** |  | [optional] 
**ComparePrevious** | **bool** |  | [optional] 
**AttachExcel** | **bool** |  | [optional] 
**ManualSendAvailableAt** | **DateTime** | When the 10-minute cooldown after the last manual send ends; null when none is running | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

