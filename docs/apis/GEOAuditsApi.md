# LLMPulse.SDK.Api.GEOAuditsApi

All URIs are relative to *https://api.llmpulse.ai/api/v1*

| Method | HTTP request | Description |
|--------|--------------|-------------|
| [**CompareGeoAuditRuns**](GEOAuditsApi.md#comparegeoauditruns) | **GET** /geo_audits/{id}/comparison | Compare two GEO audit runs |
| [**CreateGeoAudits**](GEOAuditsApi.md#creategeoaudits) | **POST** /geo_audits | Create GEO audits |
| [**DeleteGeoAudit**](GEOAuditsApi.md#deletegeoaudit) | **DELETE** /geo_audits/{id} | Delete (archive) a GEO audit |
| [**GetGeoAudit**](GEOAuditsApi.md#getgeoaudit) | **GET** /geo_audits/{id} | Get a GEO audit |
| [**GetGeoAuditRun**](GEOAuditsApi.md#getgeoauditrun) | **GET** /geo_audits/{geo_audit_id}/runs/{sequence} | Get a GEO audit run |
| [**ListGeoAlerts**](GEOAuditsApi.md#listgeoalerts) | **GET** /geo_alerts | List GEO audit alerts |
| [**ListGeoAuditFindings**](GEOAuditsApi.md#listgeoauditfindings) | **GET** /geo_audits/{geo_audit_id}/runs/{sequence}/findings | List the findings of a GEO audit run |
| [**ListGeoAuditIssues**](GEOAuditsApi.md#listgeoauditissues) | **GET** /geo_audits/{geo_audit_id}/issues | List the issues of a GEO audit |
| [**ListGeoAuditRuns**](GEOAuditsApi.md#listgeoauditruns) | **GET** /geo_audits/{geo_audit_id}/runs | List the runs of a GEO audit |
| [**ListGeoAudits**](GEOAuditsApi.md#listgeoaudits) | **GET** /geo_audits | List GEO audits |
| [**RunGeoAudit**](GEOAuditsApi.md#rungeoaudit) | **POST** /geo_audits/{geo_audit_id}/runs | Run a GEO audit now |
| [**UpdateGeoAudit**](GEOAuditsApi.md#updategeoaudit) | **PATCH** /geo_audits/{id} | Update a GEO audit |
| [**UpdateGeoAuditIssue**](GEOAuditsApi.md#updategeoauditissue) | **PATCH** /geo_audits/{geo_audit_id}/issues/{id} | Accept or reopen a GEO audit issue |

<a id="comparegeoauditruns"></a>
# **CompareGeoAuditRuns**
> GeoAuditComparison CompareGeoAuditRuns (int projectId, string id, int fromRun = null, int toRun = null)

Compare two GEO audit runs


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **id** | **string** | Audit id |  |
| **fromRun** | **int** | Run number to compare from (default the run before to_run) | [optional]  |
| **toRun** | **int** | Run number to compare to (default the latest completed run) | [optional]  |

### Return type

[**GeoAuditComparison**](GeoAuditComparison.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The comparison |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="creategeoaudits"></a>
# **CreateGeoAudits**
> GeoAuditCreateResponse CreateGeoAudits (GeoAuditCreateRequest geoAuditCreateRequest)

Create GEO audits

Creates one audit per entry of audit_types and starts the first run of each (it counts against the manual run limits: 6 per audit per hour, 200 per account per day). cadence weekly or monthly is accepted only for types whose checks are tracked run to run, and counts against the plan limit of active recurring audits (ERR_LIMIT_REACHED). Creating an audit that was archived restores it with its history. Requires a `read_write` scope API key.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **geoAuditCreateRequest** | [**GeoAuditCreateRequest**](GeoAuditCreateRequest.md) |  |  |

### Return type

[**GeoAuditCreateResponse**](GeoAuditCreateResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The created audits |  -  |
| **403** | API key lacks write permission |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="deletegeoaudit"></a>
# **DeleteGeoAudit**
> GeoAuditArchived DeleteGeoAudit (int projectId, string id)

Delete (archive) a GEO audit

Archives the audit. Requires a `read_write` scope API key and, for team members, delete permission on GEO Optimization.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **id** | **string** | Audit id |  |

### Return type

[**GeoAuditArchived**](GeoAuditArchived.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Archived |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getgeoaudit"></a>
# **GetGeoAudit**
> GeoAuditResponse GetGeoAudit (int projectId, string id)

Get a GEO audit


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **id** | **string** | Audit id |  |

### Return type

[**GeoAuditResponse**](GeoAuditResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The audit |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="getgeoauditrun"></a>
# **GetGeoAuditRun**
> GeoAuditRunDetail GetGeoAuditRun (int projectId, string geoAuditId, int sequence)

Get a GEO audit run


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **geoAuditId** | **string** | Audit id |  |
| **sequence** | **int** | Run number within the audit |  |

### Return type

[**GeoAuditRunDetail**](GeoAuditRunDetail.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The run with its result |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listgeoalerts"></a>
# **ListGeoAlerts**
> GeoAlertList ListGeoAlerts (int projectId, string auditId = null, int page = null, int perPage = null)

List GEO audit alerts


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **auditId** | **string** | Only alerts of this audit | [optional]  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |

### Return type

[**GeoAlertList**](GeoAlertList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated alerts |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listgeoauditfindings"></a>
# **ListGeoAuditFindings**
> GeoAuditFindingList ListGeoAuditFindings (int projectId, string geoAuditId, int sequence, int page = null, int perPage = null, string output = null)

List the findings of a GEO audit run


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **geoAuditId** | **string** | Audit id |  |
| **sequence** | **int** | Run number within the audit |  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

[**GeoAuditFindingList**](GeoAuditFindingList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated findings |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listgeoauditissues"></a>
# **ListGeoAuditIssues**
> GeoAuditIssueList ListGeoAuditIssues (int projectId, string geoAuditId, string state = null, int page = null, int perPage = null)

List the issues of a GEO audit


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **geoAuditId** | **string** | Audit id |  |
| **state** | **string** | open means open and not accepted; default all | [optional]  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |

### Return type

[**GeoAuditIssueList**](GeoAuditIssueList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated issues |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listgeoauditruns"></a>
# **ListGeoAuditRuns**
> GeoAuditRunList ListGeoAuditRuns (int projectId, string geoAuditId, int page = null, int perPage = null, string output = null)

List the runs of a GEO audit


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **geoAuditId** | **string** | Audit id |  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |
| **output** | **string** | Rectangular output for BI tools (Tableau, Excel, Sheets, ELT). Omit for the default nested JSON. &#39;flat&#39; returns the same metadata plus &#39;columns&#39; and &#39;rows&#39;; &#39;csv&#39; returns those rows as text/csv. Errors are always returned as JSON. | [optional]  |

### Return type

[**GeoAuditRunList**](GeoAuditRunList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated runs |  -  |
| **404** | Resource not found |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="listgeoaudits"></a>
# **ListGeoAudits**
> GeoAuditList ListGeoAudits (int projectId, string auditType = null, string status = null, string cadence = null, int page = null, int perPage = null)

List GEO audits

Lists the project's audits, most recently updated first. Archived audits are left out unless status=archived.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **auditType** | **string** |  | [optional]  |
| **status** | **string** |  | [optional]  |
| **cadence** | **string** |  | [optional]  |
| **page** | **int** |  | [optional] [default to 1] |
| **perPage** | **int** |  | [optional] [default to 20] |

### Return type

[**GeoAuditList**](GeoAuditList.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | Paginated audits |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="rungeoaudit"></a>
# **RunGeoAudit**
> GeoAuditRunResponse RunGeoAudit (int projectId, string geoAuditId)

Run a GEO audit now

Starts a run and returns it with status queued; poll GET /geo_audits/{geo_audit_id}/runs/{sequence} until status is completed, failed or unreachable. Limited to 6 manual runs per audit per rolling hour and 200 per account per day (ERR_LIMIT_REACHED); scheduled runs do not count. Requires a `read_write` scope API key.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **projectId** | **int** | Project ID |  |
| **geoAuditId** | **string** | Audit id |  |

### Return type

[**GeoAuditRunResponse**](GeoAuditRunResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **201** | The new run |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updategeoaudit"></a>
# **UpdateGeoAudit**
> GeoAuditResponse UpdateGeoAudit (string id, GeoAuditUpdateRequest geoAuditUpdateRequest)

Update a GEO audit

Updates the schedule, the email alerts or the status. Making an audit recurring or resuming it counts against the plan limit of active recurring audits (ERR_LIMIT_REACHED). Requires a `read_write` scope API key and, for team members, update permission on GEO Optimization.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **id** | **string** | Audit id |  |
| **geoAuditUpdateRequest** | [**GeoAuditUpdateRequest**](GeoAuditUpdateRequest.md) |  |  |

### Return type

[**GeoAuditResponse**](GeoAuditResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated audit |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

<a id="updategeoauditissue"></a>
# **UpdateGeoAuditIssue**
> GeoAuditIssueResponse UpdateGeoAuditIssue (string geoAuditId, int id, GeoAuditIssueUpdateRequest geoAuditIssueUpdateRequest)

Accept or reopen a GEO audit issue

Requires a `read_write` scope API key and, for team members, update permission on GEO Optimization.


### Parameters

| Name | Type | Description | Notes |
|------|------|-------------|-------|
| **geoAuditId** | **string** | Audit id |  |
| **id** | **int** | Issue id |  |
| **geoAuditIssueUpdateRequest** | [**GeoAuditIssueUpdateRequest**](GeoAuditIssueUpdateRequest.md) |  |  |

### Return type

[**GeoAuditIssueResponse**](GeoAuditIssueResponse.md)

### Authorization

[BearerAuth](../README.md#BearerAuth)

### HTTP request headers

 - **Content-Type**: application/json
 - **Accept**: application/json


### HTTP response details
| Status code | Description | Response headers |
|-------------|-------------|------------------|
| **200** | The updated issue |  -  |
| **403** | API key lacks write permission |  -  |
| **404** | Resource not found |  -  |
| **422** | Invalid parameters |  -  |

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

