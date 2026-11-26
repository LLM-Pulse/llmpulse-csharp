# LLMPulse.SDK.Model.ShoppingRow
One row of /dimensions/shopping. Fields depend on view: products (product_key, title, domain, url, merchants, currency, currency_count, min_price, max_price, avg_rating, rating_votes, appearances, is_client, best_rank, models, last_seen_at) and merchants (merchant, appearances, products, currency, min_price, max_price, avg_price, avg_rating).

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Appearances** | **int** |  | 
**ProductKey** | **string** | Stable grouping key of the product: its external id, else title: and the lowercased title (view&#x3D;products) | [optional] 
**Title** | **string** |  | [optional] 
**Domain** | **string** |  | [optional] 
**Url** | **string** |  | [optional] 
**Merchants** | **string** | The merchants the product card names (view&#x3D;products) | [optional] 
**Merchant** | **string** | The merchant (view&#x3D;merchants) | [optional] 
**Products** | **int** | Distinct products the merchant sold (view&#x3D;merchants) | [optional] 
**Currency** | **string** | Currency code the prices are in; null when no price names one | 
**CurrencyCount** | **int** | Currencies the product was priced in; above 1 the row reports its highest-priced listing (view&#x3D;products) | [optional] 
**MinPrice** | **decimal** |  | 
**MaxPrice** | **decimal** |  | 
**AvgPrice** | **decimal** | Average price in currency (view&#x3D;merchants) | [optional] 
**AvgRating** | **decimal** |  | 
**RatingVotes** | **int** | Most rating votes any listing of the product showed (view&#x3D;products) | [optional] 
**IsClient** | **bool** | Whether the product is identified as your brand&#39;s own (view&#x3D;products) | [optional] 
**BestRank** | **int** | Best rank the product got in a card list (view&#x3D;products) | [optional] 
**Models** | **List&lt;ShoppingRow.ModelsEnum&gt;** | Models that showed the product (view&#x3D;products) | [optional] 
**LastSeenAt** | **DateTime** | The latest answer that showed the product (view&#x3D;products) | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

