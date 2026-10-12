# Frequently Asked Questions

## General Questions

### What is the Enji MCP server?

A remote server that connects an AI client such as ChatGPT or Claude to Enji, the AI marketing assistant for wedding and creative pros. Without an account, the AI client can answer marketing questions from Enji's knowledge base and use Enji's free generators. Signed in to an Enji account, it can also work on your business: your marketing plan, tasks, social posts, long-form content, media, and calendar.

### Do I need to install anything?

No. It is a hosted service. Add the server URL to your AI client.

### Which AI client plans can add it?

Until Enji is listed in the client directories, it is added as a custom server. ChatGPT allows that only in Business, Enterprise, and Edu workspaces, where an admin adds it and publishes it to the workspace; Free, Plus, and Pro accounts cannot add custom servers. Claude allows custom connectors on every plan, with Team and Enterprise owners adding it for their members. Once Enji is in the directories, any plan can add it from there. The [README](../README.md) has the current steps for each client.

### Do I need an Enji account?

Not for the public server at `https://mcp.enji.co/public`. The signed-in server at `https://mcp.enji.co/mcp` needs an Enji account on a trial or paid plan. [Start a free trial](https://www.enji.co).

### Which URL should I use?

- `https://mcp.enji.co/public` if you want marketing answers and the free generators with no account.
- `https://mcp.enji.co/mcp` if you want the AI client to work inside your Enji business. It includes everything the public server does.

---

## Setup & Configuration

**Full setup guide:** [enji.co/mcp](https://www.enji.co/mcp)

### What happens when I connect the signed-in server?

Your AI client sends you to Enji to sign in. You then choose which of your businesses the AI client may work with and approve the permissions it asks for (reading your profile, reading and writing tasks, reading and writing content). You can change or revoke this any time in Enji under **Settings → Connected Apps**.

### I have several businesses in Enji. Which one does the AI client use?

The ones you shared at sign-in. If you shared more than one, the AI client asks which business a request is about, or you can name it.

### I added the connector but the AI client isn't using it. Why?

Make sure:
1. The connector is enabled in your settings, not just added
2. You told the chat you want to use Enji, or asked something Enji's tools help with

Try a specific prompt like "What marketing tasks do I have this week?" or "Generate blog ideas for my business".

### Can I use this on mobile?

Yes. Once the connector is added in your AI client, it works wherever that client runs.

### I used the old Enji AI Marketing Agent URL. Does it still work?

No. The endpoints `https://mcp.enji.co/mcp/messages`, `/mcp/sse`, and `/mcp/manifest` have been retired. Replace the saved connector with `https://mcp.enji.co/public` or `https://mcp.enji.co/mcp`.

---

## Using the Tools

### What can an AI client do with Enji?

Without sign-in:
- Answer marketing questions from Enji's knowledge base
- Generate blog and social media content ideas
- Create customer personas
- Analyze a brand voice

Signed in:
- Read your marketing plan, brand voice, and customers so ideas fit your business
- See and manage the tasks on your marketing calendar
- Draft social posts and videos in your brand voice, plan them, and schedule the ones you approve
- Write blog posts, newsletters, press releases, and show notes as Enji documents
- Use the images and videos in your Enji media library

See the [Tool Reference](./tools.md) for details.

### Will the AI client post to my social accounts?

Only when you ask it to. Posts are created as drafts. A post goes on the publishing queue only when you explicitly ask for it to be scheduled, and Enji publishes it at its time. You can hold it again as a draft at any point before then.

### Can it upload images from my computer?

Not over MCP. It can use media already in your Enji library or fetch an image or video from a public link, including Google Drive and Dropbox share links. Upload from your device in the Enji app.

### How does an AI client know when to use Enji's tools?

It decides from your request, but it helps to mention Enji when starting a new chat. For example:

- "What should I post this week?" → reads your plan and calendar
- "Should I use email marketing?" → searches Enji's knowledge base
- "Create a customer persona" → uses the persona generator

### The results are too generic. How do I get better outputs?

Signed in, ask the AI client to read your marketing context first; everything it writes then fits your business. Without sign-in, be specific:

❌ "Generate blog ideas"
✅ "Generate blog ideas for my mobile dog grooming business targeting busy pet owners in Austin, Texas"

---

## Privacy & Security

### Is my data secure?

Yes. All communication is over HTTPS. The signed-in server uses OAuth 2.0 with PKCE, the same standard the major AI clients use for their built-in connectors. Your Enji password is entered only on Enji's sign-in page, never in the AI client.

### What data does the AI client access?

Public server: only Enji's public resources and the text you provide to the generators. Nothing about you is stored.

Signed-in server: the businesses you chose at sign-in, within the permissions you approved. Your existing Enji role applies to every action. It never sees other Enji customers' data.

### Can I revoke access?

Yes, any time, in Enji under **Settings → Connected Apps**. Revoking invalidates the connection immediately. You can also remove the connector in your AI client.

### Is there a record of what the AI client changed?

Every change is confirmed in the chat, and the records it creates or changes appear in Enji like any other edit. Deleted tasks, posts, and documents are recoverable from Enji.

---

## Troubleshooting

### "Error occurred during tool execution"

This usually means:
1. The server is temporarily unavailable; try again in a moment
2. A required detail was missing; the error says which

If it persists, contact contact@enji.co

### The AI client says my plan does not allow this

The signed-in tools need an Enji business on a trial or paid plan. The error includes a link to billing.

### The AI client cannot schedule a post

The social account needs to be connected in Enji. Posts can be planned and drafted for a platform that has been added to the business, but publishing needs a live connection.

### The AI client says it doesn't have access to Enji

Make sure:
1. You added the connector
2. The connector is enabled, not just added
3. For the signed-in server, you completed sign-in and approved at least one business

---

## Billing & Pricing

### Does the Enji MCP server cost extra?

No. The public server is free. The signed-in server is included with every Enji trial and paid plan.

---

## Feature Requests & Support

### Can you add [specific feature]?

We'd love to hear your ideas:
- [Open a GitHub issue](https://github.com/enjiapp/ai-marketing-agent/issues) with your suggestion
- Email contact@enji.co
- Share feedback in the Enji app

### I found a bug. How do I report it?

1. [Open a GitHub issue](https://github.com/enjiapp/ai-marketing-agent/issues)
2. Or email contact@enji.co

Include:
- Which AI client and which server URL you used
- What you were trying to do
- What happened and what you expected
- Any error messages

### Where can I get help?

- **Documentation:** [enji.co/mcp](https://www.enji.co/mcp)
- **Help Center:** [help.enji.co](https://help.enji.co)
- **GitHub Issues:** technical problems
- **Email:** contact@enji.co for account or billing questions

---

## About Enji

### What is Enji?

Enji is the AI marketing assistant for wedding and creative pros: your marketing gets done. It builds your marketing strategy, keeps your plan and calendar, writes content in your brand voice from your own photos, schedules your social media, and tracks what is working, all in one place. The MCP server brings that assistant into ChatGPT, Claude, or any AI client you already use.

[Learn more about Enji →](https://www.enji.co)

### Who is Enji for?

Enji is built for **wedding and creative professionals**: photographers, planners, venues, florists, designers, and the other businesses that make up most of Enji's customers. Its marketing guidance, content ideas, and examples are written for that industry.

Other solopreneurs and small businesses use Enji too, and everything here works for them: coaches and consultants, service businesses, freelancers managing several clients, and small teams who want their AI assistant to know their business.

### How is the MCP server different from just using Enji?

It brings Enji into the AI client you already use. Instead of switching apps, you can ask what to work on, draft a post about last weekend's wedding that already sounds like you, and put it on your Enji calendar from the conversation. Enji remains the place where it all lives, gets reviewed, and publishes.

### Is the MCP server included in my plan?

Yes. It is included with every Enji trial and paid plan, and the public server is free for anyone. Plan details are at [enji.co](https://www.enji.co).

---

**Still have questions?** Contact contact@enji.co or visit [enji.co/mcp](https://www.enji.co/mcp)
