---
title: "Knowledge Base Automation: Custom Fields, SCIM Provisioning & AI Sync Explained"
url: "https://document360.com/blog/knowledge-base-automation/"
date: "Fri, 03 Apr 2026 14:35:04 +0000"
author: "Jenolin Johnson"
feed_url: "https://document360.com/blog/feed/"
---
<p>There&#8217;s a particular kind of frustration that quietly builds as teams grow. Not the loud, urgent kind, but the slow, grinding kind. The kind you feel when onboarding a new team member means manually adding them to a dozen tools one by one. When article ownership gets tracked in a separate spreadsheet because your documentation platform has no place for it. Where your AI assistant knows everything except the one thing you need, your own documentation. Where a support agent switches between four tabs just to draft a reply, they could have written in one. When a reader stares at a three-hundred-row table and wonders if there&#8217;s a smarter way to navigate it.</p>
<p>The March release of Document360 was designed with all of those moments in mind. Whether you&#8217;re dealing with access management across a large team, trying to connect your AI tools to your <a href="/blog/knowledge-base/" rel="noopener" target="_blank">knowledge base</a>, or simply making it easier for readers to find what they&#8217;re looking for, <a href="https://docs.document360.com/docs/march-2026-1231" rel="noopener" target="_blank">v12.3.1</a> brings something that genuinely shifts the experience.</p>
<h2 id="custom-fields-build-your-knowledge-base-around-you">Custom Fields: Build Your Knowledge Base Around Your Workflow</h2>
<p>Every knowledge base grows. And when it does, the default fields are no longer enough.</p>
<p>At some point, you need more than what the system offers out of the box. You want to tag articles by product version, assign ownership to specific contributors, mark content by release status, or attach metadata that&#8217;s unique to how your team operates. But standard fields don&#8217;t stretch that far, so teams start improvising into spreadsheets, naming conventions, and workarounds that made sense early on but quietly become a burden as the knowledge base scales.</p>
<p>Custom fields change that.</p>
<p>Document360 now lets you define your own fields from scratch. Text inputs, dropdowns, date selectors, booleans, numbers, configured to fit your actual workflow rather than a generic template. Once created, these fields show up across articles, categories, decision trees, and <a href="/blog/api-documentation/" rel="noopener" target="_blank">API documentation</a>. Contributors can fill them in, and admins decide what&#8217;s editable and what stays locked.</p>
<p>But here&#8217;s where it gets particularly useful. If you manage API documentation, you already know how much context lives outside the article itself. Authentication methods, endpoint version, deprecation status, rate limits, and more information that&#8217;s critical but has never had a clean home to live inside a standard article format. Custom fields give that data a structured, consistent place to live, and since it&#8217;s retrievable via API, your external tooling can use it.</p>
<p>This is just the first phase, with more functionality on the way. But even now, it closes a gap that teams have been quietly working around for a long time.</p>
<p><img alt="MCP and SCIM product overview graphic" class="" height="500" src="https://document360.com/wp-content/uploads/2026/04/mcp-and-scim-products.webp" width="1000" /></p>
<div class="call_to_action border-0 bg-secondary">
<div class="call_to_text">
<p>Automate your knowledge base, streamline workflows, and connect AI effortlessly with Document360</p>
<a class="cta" href="https://document360.com/request-demo/" rel="noopener" target="_blank">Book A Demo</a></div>
<div class="call_to_img"><img alt="Document360" class="alignnone size-full wp-image-2957" src="https://document360.com/wp-content/themes/document360/images/blog-call-to-action.png" /></div>
</div>
<h2 id="and-then-theres-mcp-and-scim">And then there&#8217;s MCP and SCIM.</h2>
<p>Two other major updates shipped this month, and they&#8217;re significant enough that brief bullet points wouldn&#8217;t do them justice. We&#8217;ve written dedicated posts on both.</p>
<p><a href="https://docs.document360.com/docs/mcp" rel="noopener" target="_blank">MCP</a> connects your Document360 knowledge base directly to AI assistants like Claude, ChatGPT, Copilot, and others. Instead of copy-pasting content or acting as a go-between, your AI can now search your documentation, read articles, and even create or update content inside Document360 on its own. <br />
<br />
If you haven’t read it yet, you can find the full post here: <a href="/blog/mcp-server/" rel="noopener" target="_blank">How MCP Transforms AI Documentation Workflows</a></p>
<p><img alt="SCIM simplifies user management processes" class="alignnone" height="460" src="https://document360.com/wp-content/uploads/2026/04/scim-user-management.webp" width="920" /></p>
<p><a href="https://docs.document360.com/docs/scim" rel="noopener" target="_blank">SCIM</a> takes the pain out of user management. New hire joins? Provisioned automatically. Someone leaves? Access revoked instantly, everywhere. No manual steps, no orphaned accounts, no loose ends, no cleanup queue piling up at the start of the week.</p>
<p><img alt="SCIM" class="alignnone" height="476" src="https://document360.com/wp-content/uploads/2026/04/cleanup-queue-start-of-week.webp" width="952" /></p>
<p>You can catch the full post here if you haven’t already: <a href="/blog/what-is-scim/" rel="noopener" target="_blank">SCIM Explained: Automate User Provisioning &amp; Identity Management</a></p>
<h2 id="the-rest-of-what-shipped">The rest of what shipped</h2>
<p>A few more updates worth highlighting:</p>
<ul>
	<li>The <a href="https://docs.document360.com/docs/freshdesk" rel="noopener" target="_blank"><strong>Freshdesk integration</strong></a> got a meaningful upgrade. Support agents can now generate AI-drafted replies directly within Freshdesk, pulled from your knowledge base content. They also get article suggestions relevant to the ticket they&#8217;re handling and can insert links without switching tabs. Multilingual support is built in.</li>
</ul>
<p><img alt="Interactive multilingual tables for knowledge base" class="" height="568" src="https://document360.com/wp-content/uploads/2026/04/multilingual-tables-interactive.webp" width="1010" /></p>
<ul>
	<li><a href="https://docs.document360.com/docs/tables-in-advanced-wysiwyg-editor" rel="noopener" target="_blank"><strong>Tables </strong></a>on the knowledge base site are now interactive. Readers can sort and filter columns directly on the page instead of scrolling through hundreds of rows to find one entry. It handles large datasets well, loads quickly, and doesn&#8217;t change anything about how you author content.</li>
</ul>
<div class="doc360-videoWrapper" style="padding-bottom: 56.25%; height: 0; overflow: hidden;">
  </div>
<p>&nbsp;</p>
<ul>
	<li><a href="https://docs.document360.com/docs/import-export" rel="noopener" target="_blank"><strong>Project export </strong>and <strong>import</strong> </a>received a full redesign. The category selection interface now reflects parent-child relationships clearly, supports partial selections, and includes search. Anyone who&#8217;s worked through a complex export before will notice the improvement right away.</li>
</ul>
<p><img alt="Improved complex export interface with article titles" class="" height="496" src="https://document360.com/wp-content/uploads/2026/04/complex-export-improvements.webp" width="992" /></p>
<ul>
	<li>And a few smaller but useful additions: article titles now support up to 300 characters, <a href="https://docs.document360.com/docs/ai-assistive-search-ask-eddy" rel="noopener" target="_blank">Eddy AI</a> now displays citations showing exactly which source articles it drew from, Cantonese has been added as a new supported language, and the Customer API now runs independently of the portal, so readers aren&#8217;t affected during maintenance windows</li>
</ul>
<h2 id="march-in-short">March, in short</h2>
<p>Custom fields gave teams a real structure to work with. MCP and SCIM earned their own spotlight. And the rest of what shipped made the day-to-day work feel lighter. That&#8217;s what a good release looks like.</p>
<p><em>Document360 v12.3.1 is live now. Log in to explore or check the portal to get started.</em></p><p>The post <a href="https://document360.com/blog/knowledge-base-automation/">Knowledge Base Automation: Custom Fields, SCIM Provisioning &#038; AI Sync Explained</a> appeared first on <a href="https://document360.com">Document360</a>.</p>
