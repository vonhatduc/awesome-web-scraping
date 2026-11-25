<h1 align="center">Awesome Web Scraping</h1>

<p align="center">
  <a href="https://github.com/sindresorhus/awesome"><img src="https://awesome.re/badge.svg" alt="Awesome"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-CC0--1.0-lightgrey.svg" alt="CC0-1.0"></a>
</p>

> A curated list of libraries, services and know-how for **web scraping, crawling and structured data extraction** — across Python, JavaScript, Go, Rust, Java, Ruby, PHP and C#.

Scraping is three problems wearing one coat: **fetching** a page that may not
want to be fetched, **parsing** what comes back, and **keeping it working** next
month. The list is organised that way rather than by popularity, so you can
start at the layer that is actually failing you.

## Contents

- [Hosted APIs and platforms](#hosted-apis-and-platforms)
- [Frameworks](#frameworks)
  - [Python](#python)
  - [JavaScript and TypeScript](#javascript-and-typescript)
  - [Go](#go)
  - [Rust](#rust)
  - [Java and JVM](#java-and-jvm)
  - [Ruby](#ruby)
  - [PHP](#php)
  - [C# and .NET](#c-and-net)
- [Browser automation](#browser-automation)
- [Anti-bot, fingerprints and TLS](#anti-bot-fingerprints-and-tls)
- [Parsing and content extraction](#parsing-and-content-extraction)
- [AI and LLM extraction](#ai-and-llm-extraction)
- [Proxies](#proxies)
- [CAPTCHA solving](#captcha-solving)
- [Orchestration and scale](#orchestration-and-scale)
- [Web archiving](#web-archiving)
- [Monitoring and data quality](#monitoring-and-data-quality)
- [Datasets and open sources](#datasets-and-open-sources)
- [Practice targets and bot-detection testers](#practice-targets-and-bot-detection-testers)
- [Legal and ethics](#legal-and-ethics)
- [Learning](#learning)
- [Related lists](#related-lists)
- [Contributing](#contributing)

## Hosted APIs and platforms

Someone else's problem: proxies, browsers, retries and CAPTCHAs behind one
endpoint. Worth it when the blocking, not the parsing, is what costs you time.

- [Apify](https://apify.com) — a marketplace of ready-made "actors" plus a platform to run your own; the [Crawlee](https://crawlee.dev) authors.
- [Bright Data](https://brightdata.com) — the largest proxy network, plus a Web Unlocker and scraping APIs on top of it.
- [Browse AI](https://www.browse.ai) — point-and-click robot recorder aimed at non-developers, with change monitoring.
- [Crawlbase](https://crawlbase.com) — crawling and scraping API with a generous free tier.
- [Diffbot](https://www.diffbot.com) — automatic extraction into article/product/discussion schemas, plus a knowledge graph.
- [Firecrawl](https://firecrawl.dev) — crawl a site into LLM-ready markdown; [open source](https://github.com/mendableai/firecrawl) and self-hostable.
- [Foxpull](https://foxpull.com) — describe the fields in plain English, get JSON; escalates through browser and CAPTCHA solving on its own, and the platform is self-hostable. ([Python client](https://github.com/vonhatduc/foxpull-python), [API docs](https://foxpull.com/docs/api))
- [Jina Reader](https://jina.ai/reader/) — prefix any URL with `r.jina.ai/` to get clean markdown; free tier without a key.
- [Octoparse](https://www.octoparse.com) — desktop point-and-click scraper with cloud execution.
- [Oxylabs](https://oxylabs.io) — proxies plus dedicated scraper APIs for search, e-commerce and real estate.
- [ScraperAPI](https://www.scraperapi.com) — one endpoint that handles proxies, browsers and retries.
- [ScrapingAnt](https://scrapingant.com) — headless-browser scraping API with residential proxies.
- [ScrapingBee](https://www.scrapingbee.com) — rendering-focused API with a well-documented free tier.
- [Scrapfly](https://scrapfly.io) — scraping API with anti-bot bypass and an unusually good [technical blog](https://scrapfly.io/blog/).
- [SerpApi](https://serpapi.com) — structured results from Google, Bing, Amazon and other search surfaces.
- [Steel.dev](https://steel.dev) — open-source browser API built for AI agents.
- [Zyte API](https://www.zyte.com/zyte-api/) — the Scrapy maintainers' commercial platform: proxies, bans handling and automatic extraction.

## Frameworks

### Python

- [Scrapy](https://github.com/scrapy/scrapy) — the reference crawling framework: scheduling, middlewares, pipelines, `scrapy shell`. Still the answer for anything with more than a few hundred pages.
- [requests](https://github.com/psf/requests) — the HTTP library most scrapers start with.
- [httpx](https://github.com/encode/httpx) — requests-compatible API with async and HTTP/2.
- [aiohttp](https://github.com/aio-libs/aiohttp) — async HTTP client and server.
- [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/) — forgiving HTML parsing; the gentlest place to begin.
- [parsel](https://github.com/scrapy/parsel) — Scrapy's XPath/CSS selector layer, usable on its own.
- [selectolax](https://github.com/rushter/selectolax) — Lexbor/Modest-backed parsing, several times faster than lxml for CSS selection.
- [lxml](https://github.com/lxml/lxml) — libxml2 bindings; the fast, strict option.
- [MechanicalSoup](https://github.com/MechanicalSoup/MechanicalSoup) — form filling and session handling without a browser.
- [Botasaurus](https://github.com/omkarcloud/botasaurus) — framework bundling anti-detection, caching and parallelism.
- [scrapy-playwright](https://github.com/scrapy-plugins/scrapy-playwright) — Playwright download handler for Scrapy.
- [scrapy-splash](https://github.com/scrapy-plugins/scrapy-splash) — the older Splash-based rendering integration.
- [scrapy-redis](https://github.com/rmax/scrapy-redis) — Redis-backed scheduler and dupefilter; the usual way to run Scrapy distributed.
- [Gerapy](https://github.com/Gerapy/Gerapy) — Django-based management UI for distributed Scrapy deployments.

### JavaScript and TypeScript

- [Crawlee](https://github.com/apify/crawlee) — crawling framework with request queues, session and proxy rotation, over Cheerio, Playwright or Puppeteer. Also in [Python](https://github.com/apify/crawlee-python).
- [Cheerio](https://github.com/cheeriojs/cheerio) — jQuery-flavoured server-side HTML parsing.
- [Playwright](https://github.com/microsoft/playwright) — cross-browser automation; the current default for rendered pages.
- [Puppeteer](https://github.com/puppeteer/puppeteer) — Chrome DevTools Protocol driver.
- [got-scraping](https://github.com/apify/got-scraping) — `got` with browser-like TLS and header fingerprints.
- [node-crawler](https://github.com/bda-research/node-crawler) — queue, rate limiting and Cheerio parsing in one.
- [x-ray](https://github.com/matthewmueller/x-ray) — declarative selector-to-object scraping with pagination.

### Go

- [Colly](https://github.com/gocolly/colly) — fast, callback-driven scraping framework.
- [goquery](https://github.com/PuerkitoBio/goquery) — jQuery-like document traversal.
- [chromedp](https://github.com/chromedp/chromedp) — drive Chrome over DevTools Protocol without external dependencies.
- [Katana](https://github.com/projectdiscovery/katana) — crawler built for security recon, with headless and JS parsing modes.
- [Ferret](https://github.com/MontFerret/ferret) — scraping with its own declarative query language.

### Rust

- [spider](https://github.com/spider-rs/spider) — concurrent crawler built for throughput.
- [scraper](https://github.com/causal-agent/scraper) — HTML parsing on html5ever with CSS selectors.
- [thirtyfour](https://github.com/stevepryde/thirtyfour) — async WebDriver client.
- [fantoccini](https://github.com/jonhoo/fantoccini) — high-level WebDriver client for headless browsers.

### Java and JVM

- [jsoup](https://github.com/jhy/jsoup) — HTML parsing, cleaning and CSS selection.
- [Selenium](https://github.com/SeleniumHQ/selenium) — the WebDriver standard's reference implementation.
- [Apache Nutch](https://github.com/apache/nutch) — the veteran production-scale crawler, Hadoop-friendly.
- [StormCrawler](https://github.com/apache/incubator-stormcrawler) — low-latency crawling on Apache Storm.
- [webmagic](https://github.com/code4craft/webmagic) — Scrapy-inspired framework, popular in China.
- [crawler4j](https://github.com/yasserg/crawler4j) — small multi-threaded crawler, easy to embed.
- [HtmlUnit](https://github.com/HtmlUnit/htmlunit) — GUI-less browser with its own JS engine.

### Ruby

- [Nokogiri](https://github.com/sparklemotion/nokogiri) — the HTML/XML parser everything else builds on.
- [Kimurai](https://github.com/vifreefly/kimuraframework) — Scrapy-like framework over Capybara and headless browsers.
- [Mechanize](https://github.com/sparklemotion/mechanize) — stateful browsing: forms, cookies, redirects.
- [Ferrum](https://github.com/rubycdp/ferrum) — Chrome DevTools Protocol driver with no Selenium in the way.

### PHP

- [Symfony DomCrawler](https://github.com/symfony/dom-crawler) — DOM traversal and selection; pairs with [BrowserKit](https://github.com/symfony/browser-kit) (what Goutte became).
- [Symfony Panther](https://github.com/symfony/panther) — real-browser testing and scraping over WebDriver.
- [Guzzle](https://github.com/guzzle/guzzle) — the standard HTTP client, with concurrency pools.
- [Roach PHP](https://github.com/roach-php/core) — Scrapy's architecture ported to PHP, Laravel-friendly.
- [Simple HTML DOM](https://github.com/simplehtmldom/simplehtmldom) — the beginner classic; slow, but everywhere.

### C# and .NET

- [AngleSharp](https://github.com/AngleSharp/AngleSharp) — standards-compliant HTML/CSS parsing with a real DOM.
- [Html Agility Pack](https://github.com/zzzprojects/html-agility-pack) — the long-standing tolerant parser.
- [PuppeteerSharp](https://github.com/hardkoded/puppeteer-sharp) — Puppeteer port for .NET.
- [Abot](https://github.com/sjdirect/abot) — extensible multithreaded crawler.

## Browser automation

Reach for these only when the data genuinely arrives via JavaScript — a browser
costs roughly an order of magnitude more RAM and time per page than a fetch.
Check the network tab for a JSON endpoint first.

- [Playwright](https://playwright.dev) — Chromium, Firefox and WebKit, one API, with auto-waiting that removes most flaky sleeps.
- [Puppeteer](https://pptr.dev) — Chrome-first, lighter, huge plugin ecosystem.
- [Selenium](https://www.selenium.dev) — the widest language and browser support; the standard everything else is measured against.
- [SeleniumBase](https://github.com/seleniumbase/SeleniumBase) — Selenium with a stealth-capable UC mode and a test runner.
- [nodriver](https://github.com/ultrafunkamsterdam/nodriver) — the successor to undetected-chromedriver, no WebDriver binary at all.
- [undetected-chromedriver](https://github.com/ultrafunkamsterdam/undetected-chromedriver) — patched ChromeDriver that survives common detectors.
- [Camoufox](https://github.com/daijro/camoufox) — Firefox patched at the C++ level for fingerprint spoofing, driven by Playwright.
- [puppeteer-extra-plugin-stealth](https://github.com/berstend/puppeteer-extra) — the plugin stack that hides the obvious headless tells.
- [Browserless](https://github.com/browserless/browserless) — headless Chrome as a service, self-hostable.
- [Splash](https://github.com/scrapinghub/splash) — scriptable rendering service with an HTTP API; Scrapy's traditional pairing.
- [Rod](https://github.com/go-rod/rod) — Go DevTools driver designed for scraping and automation.

## Anti-bot, fingerprints and TLS

The modern block is rarely your IP alone — it is the JA3/JA4 TLS handshake,
the HTTP/2 frame order and the header casing that no HTTP library emits the way
a browser does.

- [curl-impersonate](https://github.com/lwthiker/curl-impersonate) — curl rebuilt to reproduce Chrome and Firefox TLS handshakes exactly.
- [curl_cffi](https://github.com/lexiforest/curl_cffi) — Python bindings for it; the shortest path out of "works in the browser, 403 in code".
- [tls-client](https://github.com/bogdanfinn/tls-client) — Go client with configurable TLS fingerprints, widely wrapped.
- [hrequests](https://github.com/daijro/hrequests) — requests-shaped API with browser TLS and an embedded browser engine.
- [cloudscraper](https://github.com/venomous/cloudscraper) — solves the older Cloudflare JS challenges.
- [FlareSolverr](https://github.com/FlareSolverr/FlareSolverr) — proxy that answers challenges with a real browser and hands back the cookies.
- [fingerprint-suite](https://github.com/apify/fingerprint-suite) — generate and inject consistent browser fingerprints.
- [Scrapoxy](https://github.com/fabienvauchelles/scrapoxy) — aggregate your own cloud instances and proxy vendors behind one rotating endpoint.

## Parsing and content extraction

- [trafilatura](https://github.com/adbar/trafilatura) — main-text, metadata and date extraction; consistently at the top of published extraction benchmarks.
- [readability-lxml](https://github.com/buriy/python-readability) — the Readability algorithm, Python port.
- [Readability.js](https://github.com/mozilla/readability) — Firefox Reader Mode's own extractor.
- [Resiliparse](https://github.com/chatnoir-eu/chatnoir-resiliparse) — very fast HTML text extraction built for web-scale corpora.
- [newspaper3k](https://github.com/codelucas/newspaper) — article scraping and curation; unmaintained but still widely used.
- [extruct](https://github.com/scrapinghub/extruct) — pull JSON-LD, microdata, RDFa and Open Graph out of a page. Start here before writing selectors: a surprising number of sites hand you `schema.org/Product` for free.
- [htmldate](https://github.com/adbar/htmldate) — find a page's real publication date.
- [jusText](https://github.com/miso-belica/jusText) — boilerplate removal, the classic algorithm.
- [MarkItDown](https://github.com/microsoft/markitdown) — convert HTML, PDF, Office files and more to markdown.
- [Docling](https://github.com/docling-project/docling) — document parsing with layout and table structure, for PDFs that are really tables.
- [unstructured](https://github.com/Unstructured-IO/unstructured) — preprocessing for many document types into chunks.
- [markdownify](https://github.com/matthewwithanm/python-markdownify) — HTML to markdown, small and predictable.
- [jsonpath-ng](https://github.com/h2non/jsonpath-ng) — query the JSON blob you found in a `<script>` tag.

## AI and LLM extraction

Selectors break when the markup changes; a model reads the page the way a
person would. The trade is cost per page and non-determinism — pin a schema,
cache aggressively, and keep selectors for the pages that never move.

- [Crawl4AI](https://github.com/unclecode/crawl4ai) — crawler that outputs LLM-ready markdown, with schema-based and LLM extraction strategies.
- [ScrapeGraphAI](https://github.com/ScrapeGraphAI/Scrapegraph-ai) — build scraping pipelines from a prompt and a URL.
- [LLM Scraper](https://github.com/mishushakov/llm-scraper) — TypeScript: give it a Zod schema, get typed data off any page.
- [Firecrawl](https://github.com/mendableai/firecrawl) — crawl to markdown plus `/extract` with a JSON schema.
- [autoscraper](https://github.com/alirezamika/autoscraper) — no LLM at all: show it example values, it learns the rules. Fast and free where it fits.
- [Instructor](https://github.com/567-labs/instructor) — structured, validated outputs from LLMs; the layer that keeps extraction results typed.
- [Reader](https://github.com/jina-ai/reader) — the open source behind `r.jina.ai`.

## Proxies

- [Bright Data](https://brightdata.com), [Oxylabs](https://oxylabs.io), [Decodo](https://decodo.com) (formerly Smartproxy), [IPRoyal](https://iproyal.com), [SOAX](https://soax.com) — residential and mobile pools, priced per GB.
- [Webshare](https://www.webshare.io) — cheap datacenter proxies with a free tier; the usual first step up from your own IP.
- [ProxyScrape](https://proxyscrape.com) — free public proxy lists, with the reliability that implies.
- [proxy_pool](https://github.com/jhao104/proxy_pool) — self-hosted crawler and validator for free proxies.
- [ProxyBroker2](https://github.com/bluet/proxybroker2) — find, check and rotate public proxies from code.

## CAPTCHA solving

Solvers are legitimate for accessibility and testing work and routine in
commercial scraping; they are also the point where terms of service usually
start mattering. Check what you are agreeing to before wiring one in.

- [2Captcha](https://2captcha.com) — human-backed, broad type coverage, well-documented API.
- [CapSolver](https://www.capsolver.com) — AI-based, strong on Cloudflare Turnstile and reCAPTCHA v3.
- [Anti-Captcha](https://anti-captcha.com) — one of the oldest services, with official SDKs.
- [CapMonster Cloud](https://capmonster.cloud) — the ZennoLab service, usually the cheapest per thousand.

## Orchestration and scale

- [Scrapyd](https://github.com/scrapy/scrapyd) — deploy and schedule Scrapy spiders over HTTP.
- [ScrapydWeb](https://github.com/my8100/scrapydweb) — a web UI, log parsing and alerts for Scrapyd clusters.
- [spider-rs](https://github.com/spider-rs/spider) — when throughput per machine is the constraint.
- [Frontera](https://github.com/scrapinghub/frontera) — crawl frontier framework for large, long-running crawls.
- [Apache Airflow](https://github.com/apache/airflow) / [Prefect](https://github.com/PrefectHQ/prefect) / [Dagster](https://github.com/dagster-io/dagster) — schedule the scrape as one task in a pipeline that also loads and validates.
- [Playwright Grid](https://playwright.dev/docs/docker) and [Selenium Grid](https://www.selenium.dev/documentation/grid/) — pools of browsers, containerised.

## Web archiving

- [browsertrix-crawler](https://github.com/webrecorder/browsertrix-crawler) — high-fidelity crawling into WACZ/WARC with a real browser.
- [ArchiveBox](https://github.com/ArchiveBox/ArchiveBox) — self-hosted archiver keeping HTML, PDF, screenshots and media.
- [warcio](https://github.com/webrecorder/warcio) — read and write WARC files in Python.
- [pywb](https://github.com/webrecorder/pywb) — replay archived captures, Wayback-style.
- [Heritrix](https://github.com/internetarchive/heritrix3) — the Internet Archive's own crawler.
- [wget2](https://gitlab.com/gnuwget/wget2) and [HTTrack](https://www.httrack.com) — mirror a site with one command.

## Monitoring and data quality

A scraper that silently returns empty fields is worse than one that crashes.

- [Spidermon](https://github.com/scrapinghub/spidermon) — validation, stats monitors and alerts for Scrapy.
- [Great Expectations](https://github.com/great-expectations/great_expectations) — assertions on the dataset: nulls, ranges, distributions.
- [Pydantic](https://github.com/pydantic/pydantic) — type and coerce every record at the boundary; the cheapest bug filter here.
- [pandera](https://github.com/unionai-oss/pandera) — schema validation for dataframes.
- [changedetection.io](https://github.com/dgtlmoon/changedetection.io) — watch pages for changes and alert; also a decent site-drift detector.

## Datasets and open sources

Check these before writing a crawler — the data may already exist, licensed and
free.

- [Common Crawl](https://commoncrawl.org) — petabytes of monthly web crawl data, free on S3.
- [Public Records open data](https://huggingface.co/collections/Publicrecords/public-records-open-data-and-actors-6b05ff509ac4723032284a4e) — browsable tables of US federal grants and awards, EU and UK tenders, city council meetings, ATS job postings and IMF forecast track records, with matching Apify Actors for fresh pulls
- [Wikipedia and Wikidata dumps](https://dumps.wikimedia.org) — the full corpus, no scraping needed.
- [OpenStreetMap](https://planet.openstreetmap.org) — planet-scale geodata; [Overpass API](https://overpass-turbo.eu) for querying it live.
- [Hugging Face Datasets](https://huggingface.co/datasets) — including [FineWeb](https://huggingface.co/datasets/HuggingFaceFW/fineweb), Common Crawl already cleaned.
- [data.gov](https://data.gov) / [data.europa.eu](https://data.europa.eu) — government open data portals.
- [Internet Archive](https://github.com/internetarchive/wayback/tree/master/wayback-cdx-server) — the Wayback CDX API gives you historical snapshots of any page, going back decades.

## Practice targets and bot-detection testers

Sites that exist to be scraped, and pages that tell you what you are leaking.

- [books.toscrape.com](https://books.toscrape.com) and [quotes.toscrape.com](https://quotes.toscrape.com) — the standard sandboxes, with pagination, login and JS variants.
- [Scrape This Site](https://www.scrapethissite.com/pages/) — graded exercises from tables to AJAX.
- [Web Scraper test sites](https://webscraper.io/test-sites) — e-commerce mocks with infinite scroll and pagination.
- [httpbin](https://httpbin.org) — echoes back exactly what your client sent.
- [bot.sannysoft.com](https://bot.sannysoft.com) — the classic headless-detection checklist.
- [CreepJS](https://abrahamjuliot.github.io/creepjs/) — deep fingerprint audit, including lies your stealth plugin tells.
- [BrowserLeaks](https://browserleaks.com) — per-surface leak tests: TLS, WebGL, canvas, fonts.
- [Bot detector](https://bot-detector.rebrowser.net) — checks for CDP and automation traces.

## Legal and ethics

Not legal advice — jurisdiction, the terms you clicked, and *what* you take all
change the answer. The stable parts:

- Scraping **public** data is not itself a computer-crime violation in the US after [hiQ v. LinkedIn](https://cdn.ca9.uscourts.gov/datastore/opinions/2022/04/18/17-16783.pdf) (9th Cir. 2022) and the narrowed reading of "exceeds authorized access" in [Van Buren v. United States](https://www.supremecourt.gov/opinions/20pdf/19-783_k53l.pdf) (2021). Contract, copyright and data-protection claims are separate from that and still live.
- **Personal data is regulated regardless of how public it is** — [GDPR](https://gdpr-info.eu) applies to EU residents' data whether you scraped it or were given it. Have a lawful basis before you collect names, emails or profiles.
- **Text and data mining** has an explicit EU exception ([DSM Directive Art. 3–4](https://eur-lex.europa.eu/eli/dir/2019/790/oj)), with a machine-readable opt-out rightsholders can exercise — which is what `robots.txt` and `noai` signals are increasingly used for.
- [robots.txt](https://www.rfc-editor.org/rfc/rfc9309.html) is now a standard (RFC 9309). It is not law; ignoring it is still the fastest way to turn a technical question into a legal one.
- Rate limit yourself, identify your bot in the User-Agent with a contact URL, prefer an API or a dump where one exists, and cache so you fetch each page once.

## Learning

- [Scrapy documentation](https://docs.scrapy.org) — the tutorial is still the best single introduction to crawling properly.
- [Scrapfly blog](https://scrapfly.io/blog/) and [ScrapeOps guides](https://scrapeops.io/web-scraping-playbook/) — the most thorough free write-ups on blocking and evasion.
- [Zyte blog](https://www.zyte.com/blog/) — from the people maintaining Scrapy.
- [Apify Academy](https://docs.apify.com/academy) — free structured course, from basics to anti-scraping.
- *Web Scraping with Python* by Ryan Mitchell (O'Reilly, 3rd ed. 2024) — the standard book.
- [Playwright docs](https://playwright.dev/docs/intro) — worth reading end to end if browsers are in your stack.
- [r/webscraping](https://www.reddit.com/r/webscraping/) — where blocks get diagnosed in public.

## Related lists

- [lorien/awesome-web-scraping](https://github.com/lorien/awesome-web-scraping) — the long-running language-indexed list.
- [BruceDone/awesome-crawler](https://github.com/BruceDone/awesome-crawler) — crawlers by language.
- [niespodd/browser-fingerprinting](https://github.com/niespodd/browser-fingerprinting) — field notes on beating fingerprint checks.
- [awesome-python](https://github.com/vinta/awesome-python#web-crawling) — the crawling section.

## Contributing

Pull requests welcome — see [CONTRIBUTING.md](CONTRIBUTING.md). One entry per
line, alphabetical within a section, and a description that says what the thing
*is* rather than that it is powerful and easy to use. Dead and abandoned
projects get removed; being popular is not enough to stay.

**Disclosure:** this list is maintained by the author of
[Foxpull](https://foxpull.com), which is listed under hosted APIs alongside its
competitors. Entries are not paid for and never will be — if you think one does
not belong, open an issue and say why.

## License

[CC0 1.0](LICENSE) — to the extent possible under law, the maintainers have
waived all copyright and related rights to this list.
