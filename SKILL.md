---
name: web-search
description: Search the web for current information, recent events, news, facts, or anything that may have happened after the model's training cutoff. Use this whenever the user asks about current events, the latest news, recent developments, or anything that requires up-to-date information from the internet.
metadata:
  require-secret: true
  require-secret-description: Paste your Brave Search API key. Get a free one at https://api.search.brave.com/ (2,000 queries/month free).
  homepage: https://github.com/your-username/gemma-web-search-skill
---

# Web Search

## Instructions

Call the `run_js` tool with the following exact parameters:

- script name: index.html
- data: A JSON string with the following fields:
  - query: String. The search query. Extract the user's information need and turn it into 2-6 concise search keywords. Drop filler words like "tell me about", "what is", "I'm curious about". Include the year only if the user asked about a specific time period.
  - count: Number (optional). How many results to return. Default 5, max 10. Use 3 for simple lookups, 5-10 for research questions.

After the tool returns, summarize the findings for the user in natural language. Cite the sources by their title and URL when relevant. Do not just dump the raw results — synthesize them into a clean answer.
