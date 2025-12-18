# Enji AI Marketing Agent for ChatGPT, Claude, or other AI Clients

Connect ChatGPT, Claude, or other AI Clients to Enji's AI-powered marketing tools to get instant help with your small business marketing questions (from our years of expertise) as well as free tools to create a customer persona, brand voice, and ideas for social content (blog and social media).

## 🚀 What is This?

This is a **remote MCP (Model Context Protocol) connector** that connects ChatGPT, Claude, or other AI Clients to Enji's [AI Marketing Agent](https://www.enji.co/ai-marketing-agent). It's a hosted service - no installation required. Just add the connector URL to your AI client of choice - no authentication required.

Enji is an all-in-one marketing platform designed for small businesses and solopreneurs. Our AI marketing agent helps you:
- Get real answers to marketing questions from our knowledge base (blog, marketing questions answered database, help, and FAQs)
- Build detailed customer personas
- Define your brand voice
- Generate blog and social media content ideas

## 🔗 Quick Start

### Requirements
- An AI client such as ChatGPT, Claude, or other AI clients (may require a subscription to add a connector)

### How to Connect

**In ChatGPT:**
1. Open ChatGPT
2. Go to Settings → Apps & Connectors
3. Scroll to the bottom and click on Advanced Settings and turn on Developer Mode (if it’s not already enabled)
4. Click Back and then where it says Enabled Apps and Connectors, click Create App
5. Add the Name of Enji and for the MCP Server URL add `https://mcp.enji.co/mcp/messages`
6. Optionally add Enji's logo as the Icon
7. Set Authentication to No Auth
8. Check the box that you understand click Create
9. Let the ChatGPT chat session know you want to use Enji to do your work

**In Claude.ai or Claude Desktop:**
1. Go to **Settings** > **Connectors**
2. Click **"Add custom connector"**
3. Enter the MCP server URL: `https://mcp.enji.co/mcp/messages`
4. Click **"Add"**
5. Authenticate with your Enji account when prompted
6. Let the Claude chat session know you want to use Enji to do your work

**Other AI Clients:**
1. Open your AI client settings or connectors (might need to search for their instruction on where to add MCP connectors)
2. Connect to Enji using the server URL: `https://mcp.enji.co/mcp/message` or if it wants the manifest endpoint, connect to this url: `https://mcp.enji.co/mcp/manifest`
3. If the client asks for Authentication type, choose None
4. Let the AI client chat session know you want to use Enji to do your work

That's it! Your AI client of choice can now access Enji's marketing tools.

**Learn more:** [Full setup guide on Enji.co](https://www.enji.co/ai-marketing-agent#setup-instructions)

## 🛠️ Available Tools

Once connected, your AI Client can help you with:

| Tool | Description |
|------|-------------|
| **answer_question** | Get expert answers to marketing questions from Enji's knowledge base |
| **search_public** | Search Enji's blog, Q&A library, and help center |
| **blog_ideas** | Generate fresh blog topic ideas tailored to your business |
| **social_media_ideas** | Create engaging social media post ideas |
| **customer_persona** | Build detailed customer personas for targeting |
| **brand_voice** | Analyze your writing to define your unique brand voice |
| **search** | Search Enji's blog, Q&A library, and help center (ChatGPT spec) |
| **fetch** | Fetch a document by id (ChatGPT spec) |
| **list_resources** | Discover Enji's free marketing tools and resources |

## 💡 Example Use Cases

### Marketing Strategy Help
```
You: "How should I build a social media marketing plan?"

The AI client uses Enji's answer_question tool to provide expert guidance based on wedding industry best practices.
```

### Content Planning
```
You: "I am a coffee shop owner. Can you help me generate 10 blog ideas for me?"
AI Client: asks qualifying questions about your business.

Enji uses blog_ideas to create topic suggestions like:
- The Art of Latte Art: A Beginner's Guide
- Behind the Beans: How We Source Our Coffee
- 5 Coffee Myths Debunked by Our Baristas
```

### Customer Research
```
You: "Help me create a customer persona for my yoga studio."
AI Client: asks qualifying questions about your business and customers.

Enji uses customer_persona to build a detailed profile including demographics, struggles, and solutions.
```

See more examples in our [examples directory](./examples/).

## 📚 Documentation

* **[Enji AI Marketing Agent Documentation](https://www.enji.co/ai-marketing-agent)** - Complete guide on Enji website
* **[Tool Reference](https://github.com/enjiapp/ai-marketing-agent/blob/main/docs/tools.md)** - Detailed docs
* **[Examples](https://github.com/enjiapp/ai-marketing-agent/blob/main/examples/prompts.md)** - Sample prompts
* **[FAQ](https://github.com/enjiapp/ai-marketing-agent/blob/main/docs/faqs.md)** - Common questions and troubleshooting

## 🎯 Who Should Use This?

This connector is perfect for:
- **Small business owners** looking for marketing guidance
- **Solopreneurs** who need to create ideas for content quickly
- **Freelancers** managing multiple clients' marketing
- **Startup founders** building their marketing strategy and have questions
- **Coaches and consultants** growing their audience

## 🔒 Security & Privacy

- Enji only accesses data you explicitly provide
- All API calls are made server-to-server over HTTPS
- **Privacy Policy:** [enji.co/privacy-policy](https://www.enji.co/privacy-policy)
- **Terms of Service:** [enji.co/terms-of-service](https://www.enji.co/terms-of-service)

## 🆘 Support

Having issues? Need help?

- **Help Center:** [help.enji.co](https://help.enji.co)
- **Report Issues:** [Open a GitHub issue](https://github.com/enjiapp/ai-marketing-agent/issues)
- **Email Support:** contact@enji.co

## 🔧 Technical Details

The Enji Marketing Agent MCP server supports multiple transport protocols:

- **SSE (Server-Sent Events)** - Send GET request with `Accept: text/event-stream`
- **JSON-RPC over HTTP POST** - For clients that prefer request/response
- **Endpoints:** `https://mcp.enji.co/mcp/messages` or `https://mcp.enji.co/mcp/sse`

The server automatically detects which protocol to use based on the request headers.

## 🌟 About Enji

Enji is a small business marketing platform that creates marketing strategies, manages your marketing plan, and provides AI-powered tools for content creation and scheduling. We help businesses under $1M in revenue market themselves effectively without needing a marketing degree.

**[Learn more about Enji →](https://www.enji.co)**

## 📝 License

This repository contains documentation for connecting to Enji's hosted MCP server. The server itself is a proprietary service provided by Enji.

Documentation in this repository is licensed under [MIT License](./LICENSE).

---

**Not an Enji customer yet?** [Start your free trial →](https://www.enji.co)

**Questions about this connector?** [Read the full guide on our website →](https://www.enji.co/ai-marketing-agent)
