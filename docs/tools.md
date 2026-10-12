# Tool Reference

Every tool available through Enji's MCP servers.

- **Public tools** are served at `https://mcp.enji.co/public` with no sign-in, and are also available on the signed-in server.
- **Signed-in tools** are served at `https://mcp.enji.co/mcp` after connecting an Enji account. Every signed-in tool takes an `org_id` naming the business it acts on; `list_orgs` returns the ids. When the connection is shared with one business, the AI client fills it in for you.

Each tool is annotated for the AI client as read-only or writing. Writing tools confirm what they changed, and the AI client should confirm with you before calling one.

## Public tools

### search_enji_knowledge

Search Enji's help center, blog, and small-business marketing Q&A library for passages that answer a marketing question or explain how to do something in Enji. Returns cited passages with their page URLs and one suggested Enji resource. When nothing in the library covers the question, the result says so (`low_confidence`) so the AI client does not invent an answer.

**Parameters:**
- `query` (required): The question or topic, in your words (3 to 500 characters)
- `top_k` (optional): How many passages to return (1 to 10)

**Example:**
```
Prompt: "How do I connect Pinterest to Enji?"

The AI client calls search_enji_knowledge, answers from the help center passages,
and links the article.
```

**Best for:**
- Marketing strategy questions
- How to do something in Enji
- Finding the Enji article on a topic

---

### list_enji_resources

Enji's public resources and free tools, with their URLs: the blog, the marketing Q&A library, the help center, and the free generators.

**Parameters:** none

---

### customer_persona

Generate a structured customer persona (name, demographics, struggles, solutions) from a business description, with Enji's free Customer Persona Generator.

**Parameters:**
- `business_name` (required): The business's name (up to 100 characters)
- `customer_description` (required): Who the business sells to (10 to 1,000 characters)
- `product_description` (required): The product or service (10 to 5,000 characters)
- `age_range` (optional): Target age range, for example "25-40"
- `gender` (optional): "male", "female", or "both"
- `customer_review` (optional): A customer quote or insight (up to 5,000 characters)

**Example:**
```
Prompt: "Create a customer persona for my business coaching service."

The AI client asks for the details it needs, calls customer_persona, and returns
a persona with demographics, struggles, and how the service helps.
```

---

### brand_voice

Analyze a sample of copy to produce a brand voice summary (voice, tone, style) for consistent marketing, with Enji's free Brand Voice Generator.

**Parameters:**
- `copy_sample` (required): A sample of the business's writing (50 to 5,000 characters)

**Example:**
```
Prompt: "Analyze this copy and describe my brand voice: [paste website copy or an email]"
```

---

### social_media_ideas

Generate social media post ideas tailored to a business description, with Enji's free Social Media Idea Generator.

**Parameters:**
- `business_description` (required): What the business does and sells (10 to 5,000 characters)
- `business_name` (required): The business's name (up to 100 characters)
- `target_customers` (optional): The target audience (up to 1,000 characters)

---

### blog_ideas

Generate blog topic ideas from a business description, with Enji's free Blog Idea Generator.

**Parameters:**
- `business_description` (required): What the business does and sells (10 to 5,000 characters)
- `business_name` (required): The business's name (up to 100 characters)
- `target_customers` (optional): The target audience (up to 1,000 characters)

**Example:**
```
Prompt: "Generate blog ideas for my wedding photography business."

Returns topics organized by content pillar: education, inspiration, community, promotion.
```

---

## Signed-in tools

Scopes are what the connection asks for at sign-in. A read scope covers the listing and reading tools in its area; a write scope covers creating, changing, and deleting.

### Business (`user.read`)

| Tool | What it does |
|------|--------------|
| **list_orgs** | List the businesses this connection can act on, with your role in each. Use the id as `org_id` for other tools. |
| **list_members** | List a business's team members so work can be assigned. |
| **get_marketing_context** | Who the business is and what it is working toward: business summary and offerings, brand voice, the marketing plan (goals, objectives, customer personas, channels and posting cadence, content pillars), and current campaigns. Read this first so ideas and copy fit the business. |

### Tasks (`tasks.read`, `tasks.write`)

| Tool | What it does |
|------|--------------|
| **get_todays_tasks** | What the Today view shows for a day: tasks due or carried over, with subtasks, plus the This Week outlook. |
| **list_tasks** | List a business's marketing tasks in date order. Filter by title, state, date window, campaign, or assignment. |
| **get_task** | One task with its subtasks. |
| **create_task** | Create a task. A due date puts it on the calendar; a repeat rule makes it a repeating task. Assign with a member id from list_members. |
| **create_task_occurrence** | Create the task for one date of a repeating task so it can be completed, edited, or assigned on its own. |
| **update_task** | Change a task's title, description, dates, priority, effort, assignee, or repeat rule. |
| **complete_task** | Mark a task completed. |
| **reopen_task** | Return a completed or canceled task to open. |
| **delete_task** | Delete a task and its subtasks. Recoverable from Enji. |

### Social posts (`content.read`, `content.write`)

| Tool | What it does |
|------|--------------|
| **list_social_accounts** | The business's social accounts (Facebook, Instagram, Threads, LinkedIn, Pinterest, YouTube Shorts, TikTok) with connection status. Use the id as `account_id`. |
| **list_posts** | Posts on the calendar in date order: drafts, scheduled, posted, failed. Filter by date, status, or account. |
| **get_post** | One post with its full caption, images, planning notes, and account. |
| **plan_post** | Put a planned post on the calendar with only a topic, notes, and voice, no caption yet. |
| **create_post** | Create a post with a caption and optional library images. A draft by default; pass status `scheduled` only when the user asked for it to go out. |
| **update_post** | Change a post's time, topic, notes, voice, caption, images, or Pinterest title or board. |
| **fit_media_to_platform** | Make a copy of a library image that satisfies a platform's size and aspect rules. |
| **schedule_post** | Approve a draft so Enji publishes it at its time. Only when the user has explicitly asked. |
| **unschedule_post** | Take a scheduled post off the publishing queue and keep it as a draft. |
| **delete_post** | Take a post off the calendar and cancel its publishing. Recoverable from Enji. |

A platform must be added to the business in Enji before posts can be planned or drafted for it, and connected before a post can be scheduled.

### Long-form content (`content.read`, `content.write`)

Blog posts, email newsletters, press releases, podcast show notes, and YouTube video descriptions. Enji does not publish these; marking one posted records that you published it elsewhere.

| Tool | What it does |
|------|--------------|
| **list_documents** | List long-form content with calendar dates and statuses. |
| **get_document** | Read one document in full, its text as Markdown. |
| **plan_document** | Put a planned piece on the calendar with topic, keywords, an outline, and voice, no text yet. |
| **create_document** | Create a piece with its text ready, on the calendar at a date. |
| **update_document** | Change a document's fields, media, or date. A Markdown field replaces the whole field. |
| **set_document_status** | Move a document between planning, scheduled, and posted. |
| **delete_document** | Delete a document and remove it from the calendar. |

### Media (`content.read`, `content.write`)

| Tool | What it does |
|------|--------------|
| **list_media** | The media library, images and videos, newest first, with temporary preview links. |
| **add_media_from_url** | Fetch a JPEG or PNG from a public link (Google Drive and Dropbox share links work) into the library. |
| **add_video_from_url** | Fetch an MP4, MOV, or M4V (up to 500 MB) from a public link into the library. |
| **get_media_job** | Check whether a fetch has finished and get the media id. |

Uploads from your device go through the Enji app.

### Campaigns (`tasks.read`)

| Tool | What it does |
|------|--------------|
| **list_campaigns** | The business's campaigns with dates, offer, goals, and metrics with progress, so tasks can be filed under the right one. |

---

## Combining tools

**Example workflow (signed in):**
```
Prompt: "Plan next week's content for my wedding planning business."

The AI client might:
1. Read the business with get_marketing_context
2. Check the calendar with list_posts and list_tasks
3. Lay out ideas with plan_post for each channel
4. Draft the first one with create_post and leave it for your review
```

**Example workflow (no sign-in):**
```
Prompt: "Help me build a content strategy for my wedding planning business."

The AI client might:
1. Use search_enji_knowledge for wedding marketing guidance
2. Use customer_persona to profile the ideal client
3. Use blog_ideas and social_media_ideas for topics
```

---

**Need more help?** Visit [enji.co/mcp](https://www.enji.co/mcp)
