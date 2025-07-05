#  Project 03: Domain-Specific Search Engine with Crawling and Link Analysis

## Objective

The objective of this project is to design and implement a basic **domain-specific search engine** by:

- Crawling webpages from a selected domain  
- Building an inverted index and web connection graph  
- Implementing a search mechanism using **PageRank** or **HITS** algorithms  



## Project Domain

- **Chosen Domain:** `Football`


## Methodology

The project was divided into two main phases: **Crawling** and **Searching**.

### Crawling Phase
- Selected 8–10 football-related websites as **seed URLs**.
- Built a custom web crawler using `requests` and `BeautifulSoup`.
- Limited the crawler to **50 pages** and **20 unique visits** to avoid over-fetching.
- Extracted textual content and stored word-to-page mappings in an `inverted_index`.
- Extracted hyperlinks to build a `web_connection` graph representing the page relationships.

### Searching Phase
- Modeled the directed web graph using `networkx`.
- Applied **PageRank** to rank pages based on incoming link structures.
- Applied **HITS** to compute both **authority** and **hub** scores.
- Developed a simple **keyword-based search interface**:
  - Retrieves matching pages using `inverted_index`
  - Ranks pages using PageRank or HITS
  - Displays top results with URL and short summary



##  Implementation Steps

###  Crawling Phase
-  **Step 1:** Selected the domain: `Football`
-  **Step 2:** Chose seed websites (e.g., goal.com, espn.com/soccer)
-  **Step 3:** Added URLs to `seed_urls` list
-  **Step 4:** Ran `crawl_roots()` with crawl and visit limits
-  **Step 5:** Stored outputs:
  - `inverted_index`: words → pages
  - `web_connection`: pages → linked pages

###  Searching Phase
-  **Step 6:** Built a directed graph from `web_connection`
-  **Step 7:** Calculated **PageRank** and **HITS** scores using `networkx`
-  **Step 8:** Created a search interface:
  - User enters a query
  - Pages matching query retrieved from `inverted_index`
  - Pages ranked and displayed with scores and summaries



## Results

- Successfully crawled football-related websites and collected meaningful page data.
- Built a functioning search engine that ranks results using both PageRank and HITS.
- Tested queries like:
  - `"score"`
  - `"goal"`
  - `"player"`

Each query returned relevant URLs with associated rank scores.


## Conclusion

This project showcases a **modular and functional approach** to building a **domain-specific search engine** using:

- Web scraping and link analysis
- Inverted indexing
- Graph-based ranking via **PageRank** and **HITS**

The engine effectively ranks and retrieves domain-relevant content with minimal resources. It can be extended with features like front-end UI, TF-IDF ranking, or caching for real-time use.



## Technologies Used

- `Python`
- `BeautifulSoup`
- `requests`
- `networkx`
- `nltk`

