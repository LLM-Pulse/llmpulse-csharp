# LLMPulse.SDK.Model.OwnedMediaRow
One row of /dimensions/owned_media. Fields depend on provider and view: videos (title, url, channel_name, channel_handle, channel_url, video_id, thumbnail_url, views, published_at), channels (key, name, handle, url, avatar_url, unique_videos), posts (url, caption, owner_handle, thumbnail_url, content_type, likes, comments, views, posted_at), profiles (handle, name, url, avatar_url, followers, unique_posts), own_citations (url, citation_date, position, model), apps (domain, total_responses, rank, global_rank) and activity (date, entity_id, entity_name, entity_url, yours, citations, plus store and competitor_id where applicable). Activity rows identify a reporting-period start; entity metadata is optional, and entity_id, entity_name and entity_url can be null when unknown. Store and competitor_id appear only where applicable. Every view but own_citations carries citations and yours; videos, channels, posts and profiles carry avg_position.

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Date** | **DateOnly** | The start date of the actual reporting period (view&#x3D;activity) | [optional] 
**EntityId** | **string** | Platform entity identifier (view&#x3D;activity) | [optional] 
**EntityName** | **string** | Current entity name when known (view&#x3D;activity) | [optional] 
**EntityUrl** | **string** | Current profile, channel or app listing URL when known (view&#x3D;activity) | [optional] 
**Store** | **string** | Store selected for provider&#x3D;mobile_apps (view&#x3D;activity) | [optional] 
**CompetitorId** | **int** | Competitor identifier when the activity row represents a competitor app | [optional] 
**Title** | **string** |  | [optional] 
**Url** | **string** |  | [optional] 
**ChannelName** | **string** |  | [optional] 
**ChannelHandle** | **string** | The video&#39;s channel handle, without the @ | [optional] 
**ChannelUrl** | **string** |  | [optional] 
**VideoId** | **string** |  | [optional] 
**Key** | **string** | The channel key (handle:..., channel:... or name:...), accepted as profile by /dimensions/owned_media/citing_prompts | [optional] 
**Name** | **string** |  | [optional] 
**Handle** | **string** |  | [optional] 
**Caption** | **string** |  | [optional] 
**OwnerHandle** | **string** |  | [optional] 
**ThumbnailUrl** | **string** | The post or video image. Our cached copy where one exists, so the link does not expire | [optional] 
**AvatarUrl** | **string** | The profile or channel image. Our cached copy where one exists | [optional] 
**ContentType** | **string** | The post format on its platform: reel, post or tv on Instagram, post or pulse on LinkedIn, post elsewhere | [optional] 
**Citations** | **int** | Citations for the row; for view&#x3D;activity, the count in this reporting period | [optional] 
**UniqueVideos** | **int** |  | [optional] 
**UniquePosts** | **int** |  | [optional] 
**Followers** | **int** |  | [optional] 
**Likes** | **int** |  | [optional] 
**Comments** | **int** |  | [optional] 
**Views** | **Object** | View count as the platform reports it, a number or a numeric string, or null when unknown | [optional] 
**PublishedAt** | **string** | Publication date as the platform reports it | [optional] 
**PostedAt** | **string** | Publication date as the platform reports it (ISO 8601, or Unix seconds on TikTok) | [optional] 
**AvgPosition** | **decimal** | Average position of the citation in the answers (1 &#x3D; first); null when unknown | [optional] 
**Yours** | **bool** |  | [optional] 
**CitationDate** | **DateTime** |  | [optional] 
**Position** | **int** |  | [optional] 
**Model** | **string** |  | [optional] 
**Domain** | **string** | The app&#39;s store listing URL (provider&#x3D;mobile_apps) | [optional] 
**TotalResponses** | **int** |  | [optional] 
**Rank** | **int** |  | [optional] 
**GlobalRank** | **int** |  | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

