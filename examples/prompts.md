# Example Prompts & Workflows

Real-world examples of using Enji's MCP server with your AI client. The first section needs no account. The rest use the signed-in server at `https://mcp.enji.co/mcp`.

## Without an account

### Getting marketing advice

```
"I'm a wedding planner. Should I try email marketing?"
```

Your AI client uses `search_enji_knowledge` to answer from Enji's marketing library and links the articles it drew on.

---

```
"What are the best marketing channels for a wedding venue?"
```

---

### Blog content ideas

```
"I'm a wedding photographer in Charleston called Willow & Co. I shoot relaxed,
documentary-style weddings for couples who want candid photos over posed ones.
Generate 10 blog topic ideas for me."
```

Your AI client uses `blog_ideas` to create topics organized by content pillar (education, inspiration, community, promotion, engagement, entertainment).

---

### Social media content ideas

```
"I'm a wedding planner struggling with Instagram content. Generate 10 post ideas
that will engage couples who just got engaged and are planning for next year."
```

Your AI client uses `social_media_ideas` and can organize them by platform and day.

---

### Customer persona

```
"Help me create a customer persona for my yoga studio.

Business name: Serenity Yoga
What we offer: Beginner-friendly yoga classes, meditation workshops, and wellness coaching
Target customers: Stressed professionals looking for work-life balance
Age range: 30-50
Gender: Mostly women but some men

Here's a review from a happy customer:
'Serenity Yoga has completely changed my life. As a busy executive, I was burning out.
The instructors here understand that we're beginners and make everyone feel welcome.
Now I actually look forward to my evening classes!'"
```

Your AI client uses `customer_persona` to create a profile with demographics, struggles, and solutions.

---

### Brand voice

```
"Analyze this copy from my website and describe my brand voice:

'We're not the photographers who line everyone up and count to three. We hang back,
we notice the small stuff, and we let your day happen. Your grandmother laughing
with the flower girl, your dad losing it during the first look. That's the stuff
you'll frame. Posing is optional. Being yourselves is the whole point.'"
```

Your AI client uses `brand_voice` to describe tone, style, and voice characteristics.

---

## Signed in: your week

### What to work on

```
"What marketing tasks do I have today?"
```

Your AI client uses `get_todays_tasks` and shows what is due, carried over, and coming this week.

---

```
"Show me everything on my calendar for next week and tell me what is still missing a draft."
```

Uses `list_tasks` and `list_posts`, then compares.

---

### Managing tasks

```
"Mark the newsletter task done and add a task to update the website banner by Friday,
assigned to me."
```

Uses `complete_task` and `create_task`.

---

```
"Set up a repeating task every Monday to review last week's analytics."
```

Uses `create_task` with a repeat rule.

---

## Signed in: content that fits your business

### Start from your marketing context

```
"Read my marketing context, then suggest three posts for this week that support
my current goals."
```

Your AI client uses `get_marketing_context` for your plan, customers, brand voice, and campaigns, then suggests posts that fit.

---

### Plan a week of posts

```
"Plan a week of Instagram and Pinterest posts around our 2027 booking season. Put them on the
calendar as planned posts with a topic and notes, but don't write the captions yet."
```

Uses `list_social_accounts` and `plan_post` for each day.

---

### Draft a post

```
"Write an Instagram post about Saturday's wedding at the vineyard in our brand voice, use the
sunset portrait from my media library, and save it as a draft for Thursday at 9am."
```

Uses `get_marketing_context`, `list_media`, and `create_post`. The post stays a draft until you approve it.

---

### Approve and schedule

```
"The Thursday Instagram draft looks good. Schedule it."
```

Uses `schedule_post`. Enji publishes it at its time. "Hold it as a draft again" uses `unschedule_post`.

---

### Video posts

```
"Add this video to my library and draft an Instagram reel for Saturday with a caption
in our voice: https://drive.google.com/file/d/..."
```

Uses `add_video_from_url`, `get_media_job` to wait for the fetch, then `create_post`.

---

### Long-form content

```
"Write a 600-word blog post on how to choose a wedding photographer, in our brand voice,
and save it in Enji as a draft for next Tuesday."
```

Uses `get_marketing_context` and `create_document`.

---

```
"Open the newsletter draft, tighten the intro, and mark it scheduled for Friday."
```

Uses `get_document`, `update_document`, and `set_document_status`.

---

## Refinement

### When results aren't right

```
"The blog ideas are too generic. My clients are women over 40 dealing with digestive
issues, and my approach combines evidence-based nutrition with mindfulness.
Regenerate them with that in mind."
```

---

## Pro tips

**Start with context.** Signed in, ask the AI client to read your marketing context at the start of a session. Everything after that fits your business.

**Drafts first.** Ask for drafts and review them in the chat or in Enji. Nothing publishes until you say so.

**Be specific without an account.** The public generators only know what you tell them.

**Iterate.** Ask the AI client to refine, adjust tone, or try a different angle.

---

**Want more examples?** Check out [Enji's blog](https://www.enji.co/blog) for marketing tips and tutorials.

**Ready to try it yourself?** [Connect your AI client to Enji →](https://www.enji.co/mcp)
