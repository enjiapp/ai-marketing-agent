# Enji MCP Server for ChatGPT, Claude, and other AI clients

Connect ChatGPT, Claude, or any MCP-capable AI client to Enji, the AI marketing assistant for wedding and creative pros. Two servers are available on the same host:

| Server | URL | Sign-in | What you get |
|--------|-----|---------|--------------|
| **Enji Marketing Help** | `https://mcp.enji.co/public` | None | Answers from Enji's marketing knowledge base and the free customer persona, brand voice, social idea, and blog idea generators |
| **Enji** | `https://mcp.enji.co/mcp` | Enji account (OAuth) | Everything above plus your business: marketing plan, tasks, social posts, long-form content, media, campaigns, and the posting calendar |

Both are hosted services. There is nothing to install; add the URL to your AI client.

## 🚀 What is This?

Enji is the AI marketing assistant for wedding and creative pros: your marketing gets done. These **remote MCP (Model Context Protocol) servers** let an AI client work with Enji directly.

Without an account, the AI client can:
- Get real answers to marketing questions from Enji's knowledge base (blog, marketing Q&A library, help center)
- Build a customer persona
- Define a brand voice
- Generate blog and social media content ideas

Signed in to an Enji account, it can also:
- Read the marketing context Enji keeps for your business (strategy, customers, offers, brand voice) so every idea fits
- See what is on your marketing calendar today or this week, and create, update, and complete tasks
- Draft social posts and videos in your brand voice, using media from your Enji library, and plan them on the calendar
- Write blog posts, newsletters, press releases, and show notes as Enji documents
- Review drafts, then approve and schedule them. Enji publishes a scheduled post at its time.

Nothing publishes without you: posts are created as drafts, and only a post you approve is scheduled. Every change is recorded in Enji.

## 🔗 Quick Start

### Requirements
- An AI client that supports remote MCP servers over Streamable HTTP (ChatGPT, Claude, and most others). Adding a custom server may need a paid plan; see each client below.
- For the signed-in server, an Enji account on a trial or paid plan. [Start a free trial](https://www.enji.co).

Enji has been submitted to the Claude and ChatGPT directories. Once listed, you will be able to add it from the directory on any plan without the custom-server steps below; this page will be updated when that happens.

### How to Connect

**In ChatGPT:**

Until Enji is listed in the ChatGPT directory, it can only be added as a custom MCP server, and ChatGPT limits that to **Business, Enterprise, and Edu workspaces**. A workspace admin or owner adds it and publishes it to the workspace; members then use it. Free, Plus, and Pro accounts cannot add custom servers. Once Enji is in the directory, every plan will be able to add it from there.

Workspace admin or owner:
1. In **Workspace Settings → Permissions & Roles → Connected Data**, turn on **Create custom MCP connectors** (on Enterprise and Edu this can also be granted to specific roles)
2. Go to **[chatgpt.com/plugins](https://chatgpt.com/plugins)**, click **+**, then **Add custom MCP server**
3. Enter the name Enji and a short description
4. Under **Connection**, choose **Public endpoint** and enter `https://mcp.enji.co/public` (no sign-in) or `https://mcp.enji.co/mcp` (Enji account)
5. Set authentication to **No authentication** for the public server, or **OAuth** for the signed-in server (no client ID or secret needed)
6. Read the warning, choose **I understand and want to continue**, then **Create as a plugin**
7. Review the tools ChatGPT discovered, test it, then publish it to the workspace

Members:
1. Find Enji under the workspace's apps and connect it. For the signed-in server, sign in to Enji and choose which businesses to share
2. In a chat, open the **+** menu and enable Enji, then tell the chat you want to use it for your work

ChatGPT asks you to confirm each writing action and shows exactly what it will send. If Enji's tools change, the admin refreshes the app's tool list in workspace settings.

**In Claude.ai or Claude Desktop:**

Custom connectors are available on every Claude plan (Free accounts get one). On a Team or Enterprise plan an owner adds the connector under Organization settings → Connectors first, and members then connect to it.

1. Go to **Customize → Connectors**
2. Click **+ Add**, then **Add custom connector**
3. Enter the name Enji and the URL: `https://mcp.enji.co/public` (no sign-in) or `https://mcp.enji.co/mcp` (your Enji account), then **Continue**
4. Accept the detected authentication settings (none for the public server; sign in for the signed-in server, no client ID or secret needed) and click **Add**
5. For the signed-in server, click **Connect**, sign in to Enji, and choose which businesses to share
6. In a chat, open the **+** menu, choose **Connectors**, and turn Enji on, then tell the chat you want to use it for your work

**Other AI clients:**
1. Open the client's MCP or connector settings
2. Add the server URL above. Transport is **Streamable HTTP**; the SSE and manifest endpoints of the old server have been retired
3. The public server needs no authentication. The signed-in server uses standard OAuth 2.0 with discovery at `https://mcp.enji.co/.well-known/oauth-protected-resource/mcp`, PKCE, and client ID metadata documents; no client registration is needed
4. Tell the chat you want to use Enji for your work

**Learn more:** [Setup guide on Enji.co](https://www.enji.co/mcp)

## 🛠️ Available Tools

### Without sign-in (both servers)

| Tool | Description |
|------|-------------|
| **search_enji_knowledge** | Search Enji's help center, blog, and marketing Q&A library for passages that answer a marketing question or explain how to do something in Enji |
| **list_enji_resources** | Enji's public resources and free tools, with their URLs |
| **customer_persona** | Build a structured customer persona from a business description |
| **brand_voice** | Analyze a sample of copy to define a brand voice |
| **social_media_ideas** | Generate social media post ideas for a business |
| **blog_ideas** | Generate blog topic ideas for a business |

### Signed in (`/mcp`)

| Area | Tools |
|------|-------|
| **Business** | list_orgs, list_members, get_marketing_context |
| **Tasks** | get_todays_tasks, list_tasks, get_task, create_task, create_task_occurrence, update_task, complete_task, reopen_task, delete_task |
| **Social posts** | list_social_accounts, list_posts, get_post, plan_post, create_post, update_post, fit_media_to_platform, schedule_post, unschedule_post, delete_post |
| **Long-form content** | list_documents, get_document, plan_document, create_document, update_document, set_document_status, delete_document |
| **Media** | list_media, add_media_from_url, add_video_from_url, get_media_job |
| **Campaigns** | list_campaigns |

Every tool is annotated as read-only or writing, and every write confirms what it changed. Delete tools soft-delete, and the record stays recoverable in the Enji app. Uploads from your device go through the Enji app; the AI client can use media already in your library or at a public link.

## 💡 Example Use Cases

### Marketing questions (no sign-in)
```
You: "How should I build a social media marketing plan?"

The AI client uses search_enji_knowledge to answer from Enji's marketing library and links the full article.
```

### Content ideas (no sign-in)
```
You: "I'm a wedding florist. Give me 10 blog ideas."
AI client: asks a few questions about your business.

Enji's blog_ideas tool returns topics like:
- How to Choose Wedding Flowers That Match Your Venue
- Behind the Buckets: A Wedding Week in Our Studio
- 5 Myths About Seasonal Flowers Your Florist Wants to Debunk
```

### Your week (signed in)
```
You: "What marketing tasks do I have this week, and what should I post?"

The AI client reads your calendar with list_tasks, your plan with get_marketing_context,
and suggests posts that fit your goals and brand voice.
```

### Draft and schedule a post (signed in)
```
You: "Write an Instagram post about Saturday's wedding at the vineyard in our brand voice and put it on the calendar for Thursday at 9am."

The AI client drafts the post with create_post. Nothing goes out until you approve it with schedule_post.
```

See more in the [examples directory](./examples/).

## 📚 Documentation

* **[Enji MCP setup guide](https://www.enji.co/mcp)** on the Enji website
* **[Tool Reference](./docs/tools.md)**
* **[Examples](./examples/prompts.md)**
* **[FAQ](./docs/faqs.md)**

## 🎯 Who Should Use This?

- **Wedding and creative professionals** (photographers, planners, venues, florists, designers, calligraphers, stationers), the largest group of businesses on Enji, with marketing guidance written for their industry
- **Other solopreneurs and small business owners** who want their AI assistant to know their business
- **Freelancers and agencies** managing several clients' marketing (each business is shared separately)
- **Coaches and consultants** growing an audience

## 🔒 Security & Privacy

- The public server stores nothing about you. Requests are rate limited per IP.
- The signed-in server uses OAuth 2.0 with PKCE. You choose which businesses an AI client may access at sign-in, and you can review or revoke the connection any time in Enji under **Settings → Connected Apps**.
- Tools return data from your own businesses only, and your Enji permissions apply to every action.
- All traffic is HTTPS.
- **Privacy Policy:** [enji.co/privacy-policy](https://www.enji.co/privacy-policy)
- **Terms of Service:** [enji.co/terms-of-service](https://www.enji.co/terms-of-service)

## 🆘 Support

- **Help Center:** [help.enji.co](https://help.enji.co)
- **Report Issues:** [Open a GitHub issue](https://github.com/enjiapp/ai-marketing-agent/issues)
- **Email Support:** contact@enji.co

## 🔧 Technical Details

- **Transport:** MCP Streamable HTTP (POST JSON-RPC, SSE responses when the client asks for them). Stateless; one universal URL for every business.
- **Public server:** `https://mcp.enji.co/public`, no authentication
- **Signed-in server:** `https://mcp.enji.co/mcp`, Bearer tokens from Enji's OAuth 2.0 authorization server. Discovery: `https://mcp.enji.co/.well-known/oauth-protected-resource/mcp`. Authorization code flow with PKCE (S256), RFC 8707 resource indicators, and client ID metadata documents instead of dynamic registration.
- **Scopes:** user.read, tasks.read, tasks.write, content.read, content.write, offline_access
- **Health:** `https://mcp.enji.co/health`

The earlier endpoints `https://mcp.enji.co/mcp/messages`, `/mcp/sse`, and `/mcp/manifest` have been retired. Update any saved connector to one of the URLs above.

## 🌟 About Enji

Enji is the AI marketing assistant for wedding and creative pros: your marketing gets done. It builds your marketing strategy, keeps your plan and calendar, writes content in your brand voice from your own photos, schedules your social media, and tracks what is working. Photographers, planners, venues, florists, and designers make up most of Enji's customers, and other solopreneurs and small businesses use it too.

**[Learn more about Enji →](https://www.enji.co)**

## 📝 License

This repository contains documentation for connecting to Enji's hosted MCP servers. The servers themselves are a proprietary service provided by Enji.

Documentation in this repository is licensed under the [MIT License](./LICENSE).

---

**Not an Enji customer yet?** [Start your free trial →](https://www.enji.co)
