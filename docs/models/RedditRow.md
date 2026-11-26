# LLMPulse.SDK.Model.RedditRow
One row of /dimensions/reddit. Fields depend on view: subreddits (subreddit, citations, unique_authors, positive, negative, neutral, positive_pct, negative_pct, yours, url), authors (author, citations, subreddits, extra_subreddits, leaning, positive, negative, neutral, brands, yours, url), threads (url, title, subreddit, author, subreddit_yours, author_yours, yours, citations, latest_cited_at, upvotes, comments, avg_position, sentiment, archived, posted_at) and breakdowns (breakdown, key, count, pct).

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**Subreddit** | **string** | Subreddit name without the r/ prefix; null on a thread whose subreddit is unknown | [optional] 
**Author** | **string** | Reddit username; null on a thread whose author is unknown | [optional] 
**Url** | **string** | The subreddit, author profile or thread URL | [optional] 
**Title** | **string** | Thread title, read from the post or its URL (view&#x3D;threads) | [optional] 
**Citations** | **int** | Reddit citations of the row in the window | [optional] 
**UniqueAuthors** | **int** | Distinct authors cited in the subreddit (view&#x3D;subreddits) | [optional] 
**Positive** | **int** | Citations in answers with a positive or very positive sentiment | [optional] 
**Negative** | **int** | Citations in answers with a negative or very negative sentiment | [optional] 
**Neutral** | **int** | Citations in answers with a neutral sentiment | [optional] 
**PositivePct** | **decimal** | positive over the rated citations, 0-100; null when none is rated (view&#x3D;subreddits) | [optional] 
**NegativePct** | **decimal** | negative over the rated citations, 0-100; null when none is rated (view&#x3D;subreddits) | [optional] 
**Yours** | **bool** | Whether the account claims the subreddit or author as its own (on threads, either of them) | [optional] 
**Subreddits** | **List&lt;string&gt;** | The first subreddits the author was cited in (view&#x3D;authors) | [optional] 
**ExtraSubreddits** | **int** | Further subreddits the author was cited in, beyond those listed (view&#x3D;authors) | [optional] 
**Leaning** | **string** | positive, negative or neutral, whichever sentiment has more of the author&#39;s citations (view&#x3D;authors) | [optional] 
**Brands** | [**List&lt;RedditAuthorBrand&gt;**](RedditAuthorBrand.md) | Brands the content of the author&#39;s cited posts names, your own first (view&#x3D;authors) | [optional] 
**SubredditYours** | **bool** | Whether the account claims the thread&#39;s subreddit (view&#x3D;threads) | [optional] 
**AuthorYours** | **bool** | Whether the account claims the thread&#39;s author (view&#x3D;threads) | [optional] 
**LatestCitedAt** | **DateTime** | The thread&#39;s most recent citation (view&#x3D;threads) | [optional] 
**Upvotes** | **Object** | Upvotes as the scraped post reports them, a number or a numeric string, or null when unknown (view&#x3D;threads) | [optional] 
**Comments** | **Object** | Comment count as the scraped post reports it, a number or a numeric string, or null when unknown (view&#x3D;threads) | [optional] 
**AvgPosition** | **decimal** | Average rank of the thread&#39;s citations, 1 &#x3D; first; null when no citation has a visible rank (view&#x3D;threads) | [optional] 
**Sentiment** | **string** | The most frequent sentiment of the answers that cite the thread; null when none is rated (view&#x3D;threads) | [optional] 
**Archived** | **Object** | Whether the thread is archived as the scraped post reports it, usually a boolean, or null when unknown (view&#x3D;threads) | [optional] 
**PostedAt** | **DateTime** | When the thread was posted; null when unknown (view&#x3D;threads) | [optional] 
**Breakdown** | **string** | sentiment, model or country (view&#x3D;breakdowns) | [optional] 
**Key** | **string** | The slice, a sentiment label, a model or an uppercase country code (view&#x3D;breakdowns) | [optional] 
**Count** | **int** | Reddit citations in the slice (view&#x3D;breakdowns) | [optional] 
**Pct** | **decimal** | Share of the slice within its breakdown, 0-100 (view&#x3D;breakdowns) | [optional] 

[[Back to Model list]](../../README.md#documentation-for-models) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to README]](../../README.md)

