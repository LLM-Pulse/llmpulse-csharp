# LLMPulse.SDK.Api.WebhooksApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CreateWebhook**](WebhooksApi.md#createwebhook) | **POST** /webhooks | Create a webhook subscription |
| [**DeleteWebhook**](WebhooksApi.md#deletewebhook) | **DELETE** /webhooks/{id} | Delete a webhook subscription |
| [**ListWebhooks**](WebhooksApi.md#listwebhooks) | **GET** /webhooks | List webhook subscriptions |
| [**SampleWebhookPayloads**](WebhooksApi.md#samplewebhookpayloads) | **GET** /webhooks/sample/{event_type} | Sample event payloads |

<a id="createwebhook"></a>
# **CreateWebhook**
> CreateWebhook201Response CreateWebhook (CreateWebhookRequest createWebhookRequest)

Create a webhook subscription

Subscribes a public HTTPS URL to a project event. LLM Pulse POSTs a JSON envelope (`event`, `occurred_at`, `project_id`, `subscription_id`, `data`) to the URL every time the event occurs, signed via the `X-LLMPulse-Signature` header (HMAC-SHA256 of the raw body computed with the subscription secret). Failed deliveries are retried 5 times with backoff; subscriptions auto-disable after 20 consecutive failed deliveries. Idempotent for the same project + event + URL. Requires a `read_write` scope API key and the Scale plan or above.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **createWebhookRequest** | [**CreateWebhookRequest**](CreateWebhookRequest.md) |  |  |

### Return type

[**CreateWebhook201Response**](CreateWebhook201Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | Created. The signing secret is only returned by this endpoint. |  -  |
| **401** | Authentication failed |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="deletewebhook"></a>
# **DeleteWebhook**
> DeleteWebhook200Response DeleteWebhook (int id)

Delete a webhook subscription

Deletes a webhook subscription; the target URL stops receiving events immediately. Requires a `read_write` scope API key and the Scale plan or above.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **int** |  |  |

### Return type

[**DeleteWebhook200Response**](DeleteWebhook200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **401** | Authentication failed |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listwebhooks"></a>
# **ListWebhooks**
> ListWebhooks200Response ListWebhooks (int projectId = null, int page = null, int perPage = null)

List webhook subscriptions

Lists active webhook subscriptions for the account, optionally filtered by project. Requires the Scale plan or above.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Optional project filter | [optional]  |
| **page** | **int** |  | [optional]  |
| **perPage** | **int** | Max 100 | [optional]  |

### Return type

[**ListWebhooks200Response**](ListWebhooks200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **401** | Authentication failed |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="samplewebhookpayloads"></a>
# **SampleWebhookPayloads**
> SampleWebhookPayloads200Response SampleWebhookPayloads (string eventType, int projectId)

Sample event payloads

Returns up to 3 example event payloads for the event type, built from the project's most recent real data (or a static sample when the project has no data). Used by integration editors such as the Zapier sample loader. Requires the Scale plan or above.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **eventType** | **string** |  |  |
| **projectId** | **int** |  |  |

### Return type

[**SampleWebhookPayloads200Response**](SampleWebhookPayloads200Response.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | OK |  -  |
| **401** | Authentication failed |  -  |
| **403** | Endpoint requires a higher plan tier |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

