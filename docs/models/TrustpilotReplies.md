# LLMPulse.SDK.Model.TrustpilotReplies
provider=trustpilot only. How the brand answers its Trustpilot reviews, on the profile of the project's own domain, among the reviews LLM Pulse holds for it (the newest ones from each monthly read, not every review on Trustpilot), whatever the date window. Every field is null until the profile has been read

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ReviewsHeld** | **int** | Reviews held for the profile | [optional] 
**RepliedCount** | **int** | Reviews held that the brand replied to | [optional] 
**NotRepliedCount** | **int** | Reviews held that the brand has not replied to | [optional] 
**ReplyRatePct** | **decimal** | replied_count over reviews_held, on a 0-100 scale; null when no review is held | [optional] 
**MedianReplyHours** | **decimal** | Median hours from publication to reply over the replied reviews held that carry both dates (a reply dated before its review is left out); null when there is none | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

