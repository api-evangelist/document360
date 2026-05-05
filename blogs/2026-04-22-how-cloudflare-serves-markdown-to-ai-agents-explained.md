---
title: "How Cloudflare Serves Markdown to AI Agents Explained"
url: "https://document360.com/blog/cloudflare-markdown-for-ai-agents/"
date: "Wed, 22 Apr 2026 11:41:55 +0000"
author: "Selvaraaju Murugesan"
feed_url: "https://document360.com/blog/feed/"
---
<p>Cloudflare envisages that AI agents’ traffic will surpass human traffic to the documentation site. However, many documentation sites still serve HTML content to AI agents, while they prefer <a href="/blog/introductory-guide-to-markdown-for-documentation-writers/" rel="noopener" target="_blank">Markdown</a>. <span style="margin: 0px; padding: 0px;">Cloudflare <span style="margin: 0px; padding: 0px;">recently <a href="https://blog.cloudflare.com/markdown-for-agents/" rel="nofollow noopener noreferrer" target="_blank">introduced</a> a feature that serves a Markdown version of the documentation article when</span> requested by AI agents.</span> Cloudflare automatically converts HTML format to Markdown using <a href="https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Content_negotiation" rel="nofollow noopener noreferrer" target="_blank">content negotiation</a> headers.</p>
<p>If the AI agent makes an HTTP call to retrieve the documentation article&#8217;s content, it needs to add an Accept negotiation header with text/markdown as one of the options. Cloudflare will detect this, fetch the original HTML version from the origin, and convert it to markdown before serving it to the AI agent.</p>
<h2 id="key-content-translation-problem">Key Content Translation Problem</h2>
<p>The high-level architecture of the solution is shown below</p>
<p><img alt="High-level architecture diagram of Cloudflare solution" class="" height="375" src="https://document360.com/wp-content/uploads/2026/04/cloudflare-architecture-solution.webp" width="918" /></p>
<p>Cloudflare&#8217;s feature is elegant. However, it suffers from several content translation problems, such as</p>
<h3>1. Unnecessary information is being added to the content</h3>
<p>Some interactive elements are included in the <a href="https://docs.document360.com/docs/markdown-editor-overview" rel="noopener" target="_blank">Markdown</a> content, including a search button, read-aloud, and feedback. This type of information should be removed before giving it to AI agents.</p>
<p><img alt="Interactive elements not processing correctly" src="https://document360.com/wp-content/uploads/2026/04/interactive-elements-not-processing.webp" /></p>
<h3>2. Interactive elements are not being processed correctly</h3>
<p>In many documentation sites, there is a chance that they may contain interactive elements such as dropdown lists, tabs, and collapsible elements for displaying content based on user input. The content for those elements is stored in JavaScript and is loaded dynamically. For example, the screenshot shows tabs as interactive elements.</p>
<p><img alt="Screenshot of Cloudflare interactive tabs" class="" height="558" src="https://document360.com/wp-content/uploads/2026/04/cloudflare-screenshot-interactive-tabs.webp" width="1073" /></p>
<p>When an AI agent requests this article, Cloudflare serves an inconsistent markdown format as shown below</p>
<p><img alt="Inconsistent markdown format example from Cloudflare" class="" height="743" src="https://document360.com/wp-content/uploads/2026/04/cloudflare-markdown-format-issues.webp" width="1028" /></p>
<p>This adds another layer of complexity for AI agents to understand this markdown content.</p>
<h3>3. No good hierarchy of headings with proper tags from H1 to H6</h3>
<p>Cloudflare’s conversion loses information on headings and topics. H1 tags are not followed by H2 and so on. This mismatched content hierarchy is shown below:</p>
<p><img alt="Mismatched content hierarchy in API documentation" src="https://document360.com/wp-content/uploads/2026/04/api-documentation-raw-data.webp" /></p>
<h3>4. API documentation is served as raw data rather than YAML</h3>
<p>API endpoint references are converted to raw data rather than to YAML with proper indentation, so AI agents can use the API reference to build integration pipelines.</p>
<p>An example of a scrambled <a href="/blog/api-documentation/" rel="noopener" target="_blank">API definition</a> is shown below<br />
<img alt="Scrambled API definition example for Anthropic" src="https://document360.com/wp-content/uploads/2026/04/anthropic-api-example.webp" /></p>
<p>For example, <a href="https://platform.claude.com/docs/en/agents-and-tools/tool-use/bash-tool.md" rel="nofollow noopener noreferrer" target="_blank">Anthropic API references</a> are served neatly in markdown format as</p>
<p><img alt="Anthropic API markdown request example" src="https://document360.com/wp-content/uploads/2026/04/anthropic-api-markdown-request.webp" /></p>
<div class="call_to_action border-0 bg-secondary">
<div class="call_to_text">
<p>Build AI-ready documentation that goes beyond basic Markdown conversion with Document360.</p>
<a class="cta" href="https://document360.com/signup/" rel="noopener" target="_blank">GET STARTED</a></div>
<div class="call_to_img"><img alt="Document360" class="alignnone size-full wp-image-2957" src="https://document360.com/wp-content/themes/document360/images/blog-call-to-action.png" /></div>
</div>
<h2 id="how-ai-agents-request-markdown-using-accept-header">How AI Agents Request Markdown Using Accept Headers</h2>
<p>Modern -day AI agents not only use Accept headers in the request headers; they might also try different methods, such as</p>
<ol>
	<li>Adding URL parameter ?format=markdown</li>
	<li>Adding X-Response-Format: markdown</li>
	<li>Adding .md extension to the slug to access the markdown version</li>
</ol>
<p>The above methods do not work for Cloudflare functionality. It is recommended to build your documentation server to support all functionality for serving Markdown rather than relying on Cloudflare&#8217;s feature for converting HTML to Markdown. Cloudflare also intelligently adds content-length, x-<a href="/blog/introductory-guide-to-markdown-for-documentation-writers/" rel="noopener" target="_blank">markdown</a>-tokens, and x-original-tokens to show how many tokens it has saved. This also helps AI agents adapt if they have inherent limits on truncating content due to a limited context window size. The response header shows all information</p>
<p><img alt="AI agent analytics for documentation strategy" src="https://document360.com/wp-content/uploads/2026/04/using-ai-agent-analytics.webp" /></p>
<h2 id="using-ai-agent-analytics-to-improve-documentation">Using AI Agent Analytics to Improve Documentation Strategy</h2>
<p>All the AI agent traffic data offers rich insights. Insights into the number of requests, AI agent client origin, list of popular documentation articles, and specific patterns in accessing documentation help technical writers to focus on the right set of high-value documentation articles. The AI agent traffic data also helps customers to understand the trend in consumption of their documentation. If the AI agent is surpassing human traffic, then it is high time to rethink documentation from the ground up, as your primary customers are AI agents and their characteristics of consumption are different from those of <a href="/blog/documentation-for-humans-and-ai-agents/" rel="noopener" target="_blank">human</a> readers.</p>
<p>Also, AI agent analytics helps technical writers to restructure documentation so that it helps AI agents accomplish activities. Thus, it is vital to keep the high-value documentation up to date and accurate. It is now easier to trace the documentation value chain because technical writers can quantify the value of documentation.</p>
<h2>Should You Rely on Cloudflare Markdown or Build Your Own?</h2>
<p>Even though Cloudflare offers an option to convert HTML files into markdown format for AI Agent use, it is recommended to implement this functionality in your own server. This is due to content loss, inconsistent content hierarchy, and raw API reference issues. Also, serving markdown for your own documentation server offers a good insight into AI agent behavior and rich analytics that can be used to refine documentation content. <a href="https://docs.document360.com/docs/analytics" rel="noopener" target="_blank">Rich analytics</a> helps technical writers to optimize the content length and focus on the right content. This ensures that AI agents are deriving value from documentation to accomplish tasks.</p><p>The post <a href="https://document360.com/blog/cloudflare-markdown-for-ai-agents/">How Cloudflare Serves Markdown to AI Agents Explained</a> appeared first on <a href="https://document360.com">Document360</a>.</p>
