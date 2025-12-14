# Frequently Asked Questions

## General Questions

### What is the Enji AI Marketing Agent?

It's a remote server that connects an AI Client such as ChatGPT and Claude to Enji's free marketing tools and knowledge base. Once connected, the AI client can help you with marketing questions, content creation ideas, customer research, creating a brand voice, and more.

### Do I need to install anything?

No! This is a hosted service. You just need to add the Enji AI Marketing Agent connector URL to your AI client.

### Do I need an Enji account?

No. You do not need an active Enji account to use the connector.

---

## Setup & Configuration

**Full setup guide:** [enji.co/ai-marketing-agent](https://www.enji.co/ai-marketing-agent)

### I added the Enji AI Marketing Agent connector but the AI client isn't using it. Why?

Make sure you:
1. The connector is enabled in your settings and you asked the client to use Enji's connector
2. You're asking your AI client questions that would benefit from Enji's tools

Try a specific prompt like: "Generate blog ideas for my business"

### Can I use this on mobile?

Yes! Once you've connected the Enji AI Marketing Agent connector in your AI client, it works across web and mobile.

---

## Using the Tools

### What can an AI client do with Enji?

It can:
- Answer marketing questions using Enji's knowledge base
- Generate blog and social media content ideas
- Create customer personas
- Analyze your brand voice
- Search Enji's resources

See the [Tool Reference](../docs/tools.md) for details.

### How does an AI client know when to use Enji's tools?

An AI client automatically determines when Enji's tools would be helpful based on your questions - but it is always good to let it know when you want to add Enji into a new chat session. For example:

- "Should I use email marketing?" → Uses `answer_question`
- "Generate blog ideas for my business" → Uses `blog_ideas`
- "Create a customer persona" → Uses `customer_persona`

### Can I use multiple Enji tools in one conversation?

Absolutely! Your AI client can chain multiple tools together. For example:

"Create a complete marketing strategy for my yoga studio"

The AI client might use `customer_persona`, `blog_ideas`, `social_media_ideas`, and `answer_question` all in one response.

### The results are too generic. How do I get better outputs?

Be more specific! Include:
- Details about your business and industry
- Your target customer demographics
- Your unique positioning or approach
- Any constraints or preferences

Example:
❌ "Generate blog ideas"
✅ "Generate blog ideas for my mobile dog grooming business targeting busy pet owners in Austin, Texas"

---

## Privacy & Security

### Is my data secure?

Yes. The connector is not authenticating with your Enji account and all communication happens over secure HTTPS.

### What data does the AI client access?

It can only access:
- Public Enji resources (blog, Q&A, help center)
- Free tools to generate content based on information you provide

The AI client does NOT access:
- Your Enji account data
- Your saved marketing plans
- Your scheduled social media posts
- Any personal information

### Can I revoke access?

Yes, anytime. Just disconnect the connector in your AI client's settings.

---

## Troubleshooting

### "Error occurred during tool execution"

This usually means:
1. Server temporarily unavailable - try again in a moment
2. Invalid parameters - make sure you're providing required information

If it persists, contact contact@enji.co

### The AI client says it doesn't have access to Enji

Make sure:
1. You've added the connector
2. The connector is enabled (not just added)

---

## Billing & Pricing

### Does the Enji connector cost extra?

No. It is free to use the Enji AI Marketing Agent and connector.

---

## Feature Requests & Support

### Can you add [specific feature]?

We'd love to hear your ideas! Please:
- [Open a GitHub issue](https://github.com/enjiapp/ai-marketing-agent/issues) with your suggestion
- Email us at contact@enji.co
- Share feedback in the Enji app

### I found a bug. How do I report it?

Please report bugs by:
1. [Opening a GitHub issue](https://github.com/enjiapp/ai-marketing-agent/issues)
2. Emailing contact@enji.co with details about what happened

Include:
- What you were trying to do
- What happened vs. what you expected
- Any error messages
- Screenshots if applicable

### Where can I get help?

- **Documentation:** [enji.co/ai-marketing-agent](https://www.enji.co/ai-marketing-agent)
- **Help Center:** [help.enji.co](https://help.enji.co)
- **GitHub Issues:** Report technical problems
- **Email:** contact@enji.co for account or billing questions

---

## About Enji

### What is Enji?

Enji is an all-in-one marketing platform designed specifically for small businesses and solopreneurs. We help you create marketing strategies, manage your marketing plan, create content, schedule social media, manage your brand, and track your KPIs - all in one place.

[Learn more about Enji →](https://www.enji.co)

### Who is Enji for?

Enji is perfect for:
- Small business owners with a small team
- Solopreneurs managing their own marketing
- Freelancers juggling multiple clients
- Coaches and consultants building their audience
- Service-based businesses (not e-commerce focused)

### How is the Enji AI Marketing Agent connector different from just using Enji?

The connector lets you access Enji's AI tools directly within AI client conversations. Instead of switching between apps, you can:
- Ask marketing questions and get Enji-powered answers
- Generate content ideas without leaving your conversation
- Combine Enji's marketing expertise with your AI client's general capabilities

### I'm not an Enji customer yet. Can I try it?

Yes! [Start a free trial](https://www.enji.co) to explore Enji's platform.

---

**Still have questions?** Contact us at contact@enji.co or visit [enji.co/ai-marketing-agent](https://www.enji.co/ai-marketing-agent)
