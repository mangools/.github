# Mangools

[Mangools](https://mangools.com) makes SEO tools that are simple to use and affordable. Since 2014, more than 2.8 million SEO specialists, agencies and business owners have used them to find keywords they can rank for, study search results, track rankings and check backlinks. Mangools is built by a team in Bratislava, Slovakia.

This GitHub organization holds the code we publish for developers: the OpenAPI specification of the Mangools API, the official SDKs (client libraries for Python and TypeScript), an n8n community node and a skill for Claude. They give you the same data the Mangools apps show, in your own code, workflows and AI assistants.

## The Mangools tools

- [KWFinder](https://mangools.com/kwfinder/) is a keyword research tool. It finds keyword ideas with search volume, keyword difficulty, cost per click (CPC) and trends from a database of more than 2.5 billion keywords, for over 65,000 city-level locations.
- [SERPChecker](https://mangools.com/serpchecker/) analyzes search results for any location, with SERP features and the SEO metrics of every ranking page.
- [SERPWatcher](https://mangools.com/serpwatcher/) tracks your rankings in Google, weekly or daily on the Agency plan, with shareable reports and alerts on important changes.
- [LinkMiner](https://mangools.com/linkminer/) is a backlink checker that shows the links of any website and the best opportunities among your competitors' backlinks.
- [SiteProfiler](https://mangools.com/siteprofiler/) gives the main SEO metrics of any domain: authority, backlink profile, top content and competitors.
- [AI Search Watcher](https://mangools.com/ai-search-watcher) tracks how often and where your brand appears in answers from ChatGPT, Google AI Overviews and other AI search engines.

There are also free tools, such as the [SERP Simulator](https://mangools.com/free-seo-tools/serp-simulator), the [AI Search Grader](https://mangools.com/ai-search-grader), the [Reddit Threads Finder](https://mangools.com/reddit-threads-finder) and the [SEO browser extension](https://mangools.com/seo-extension) for Chrome and Firefox. Plans and prices are at [mangools.com/plans-and-pricing](https://mangools.com/plans-and-pricing).

## Mangools API

The [Mangools API](https://mangools.com/api) is an HTTP API that returns JSON with the data of all six tools: keyword metrics, SERPs, rankings, backlinks, domain profiles and visibility in AI answers.

- [API documentation](https://apidocs.mangools.com) describes every endpoint and has a Try it panel, so you can send a real request from the docs with your API key.
- [api-spec](https://github.com/mangools/api-spec) is the OpenAPI 3.0 specification, a daily mirror of [api.mangools.com/v3/openapi.json](https://api.mangools.com/v3/openapi.json). Point a code generator, an HTTP client or an agent framework at it.
- [sdk-python](https://github.com/mangools/sdk-python) is the Python SDK: typed, based on httpx, generated from the spec. Install it with `pip install mangools`.
- [api-client-typescript](https://github.com/mangools/api-client-typescript) is the TypeScript SDK for Node 18 and newer, typed from the spec and based on fetch. Install it with `npm install mangools-api-client`.
- [Postman collection](https://www.postman.com/mangools-7057526/mangools-api) holds every endpoint in a public workspace that you can fork and use without writing code.

A short example in Python:

```python
import os
from mangools import MangoolsClient
from mangools.api.kwfinder import get_kwfinder_related_keywords

client = MangoolsClient(api_key=os.environ["MANGOOLS_API_KEY"])
related = get_kwfinder_related_keywords.sync(client=client, kw="seo tools")
for keyword in related.keywords[:5]:
    print(keyword.kw, keyword.sv, keyword.cpc, keyword.seo)
```

## AI assistants and automation

- The [Mangools MCP server](https://mangools.com/mcp) connects Claude, ChatGPT, Cursor, n8n and other AI clients to Mangools data. The assistant can then look up keywords, check a SERP or read your rank tracking while it works.
- [n8n-nodes-mangools](https://github.com/mangools/n8n-nodes-mangools) is an n8n community node with 25 read-only operations across all six tools, which also works as a tool for AI agents. The [n8n tutorial](https://apidocs.mangools.com/integrations/n8n/) has three workflows you can import: keyword research on demand, a weekly rank report and an AI SEO assistant.
- [seo-skills](https://github.com/mangools/seo-skills) is an SEO skill for Claude. It runs keyword research, a competitor gap analysis and a prioritized content plan on live Mangools data, in Claude chat, Cowork and Claude Code.

## Getting started

1. Sign in or [create a free Mangools account](https://mangools.com/users/sign_up).
2. Copy your API key at [mangools.com/api-token](https://mangools.com/api-token).
3. Send the key in the `x-access-token` header of every request. [Authentication](https://apidocs.mangools.com/authentication) has the details, and [Rate limits](https://apidocs.mangools.com/rate-limits) explains how to pace requests.

## Learn SEO

The [Mangools blog](https://mangools.com/blog) and [Learn SEO](https://mangools.com/blog/learn-seo) have free guides on keyword research, on-page SEO and link building, written for beginners and practitioners.

## Contact

Found a bug in an SDK, the node or the spec? Open an issue in that repository. For anything else, write to us at [mangools.com/contact](https://mangools.com/contact).
