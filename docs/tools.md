# Tool Reference

Complete documentation for all tools available through the Enji MCP connector.

## answer_question

Get expert answers to marketing questions based on Enji's knowledge base of blog posts, Q&A library, and help center content.

**Parameters:**
- `question` (required): Your marketing question
- `top_k` (optional): Number of results to consider (1-20, default: 6)

**Example:**
```
Prompt: "Should I use email marketing for my bakery business?"

The AI client calls answer_question and provides expert guidance based on 
Enji's marketing content.
```

**Best For:**
- Getting strategic marketing advice
- Learning about specific marketing channels
- Understanding marketing concepts
- Sspecific marketing questions

---

## blog_ideas

Generate blog topic ideas tailored to your business and audience.

**Parameters:**
- `business_description` (required): What your business does (10-5000 chars)
- `business_name` (required): Your business name (max 100 chars)
- `target_customers` (optional): Description of your target audience

**Example:**
```
Prompt: "Generate blog ideas for my dog grooming business"

AI client calls blog_ideas with:
{
  "business_description": "Mobile dog grooming service...",
  "business_name": "Pampered Paws",
  "target_customers": "Dog owners who value convenience..."
}

Returns 10 blog topics organized by content pillar:
- Education: "Understanding Your Dog's Coat Type"
- Inspiration: "Amazing Grooming Transformations"
- Community: "Supporting Local Pet Rescues"
- etc.
```

**Best For:**
- Content calendar planning
- Overcoming writer's block
- Diversifying your content strategy
- SEO content ideas

---

## social_media_ideas

Generate social media post ideas for your business.

**Parameters:**
- `business_description` (required): What your business does (10-5000 chars)
- `business_name` (required): Your business name (max 100 chars)
- `target_customers` (optional): Description of your target audience

**Example:**
```
Prompt: "Create social media ideas for my handmade jewelry business"

Returns platform-specific post ideas organized by content pillar:
- Behind-the-scenes content
- Product showcases
- Customer stories
- Tips and education
- Engagement posts
```

**Best For:**
- Social media content planning
- Maintaining consistent posting
- Engaging your audience
- Platform-specific content

---

## customer_persona

Create detailed customer personas to better understand and target your ideal customers.

**Parameters:**
- `business_name` (required): Your business name (max 100 chars)
- `customer_description` (required): Who you sell to (10-1000 chars)
- `product_description` (required): Your product/service description (10-5000 chars)
- `age_range` (optional): Target age range (e.g., "25-40")
- `gender` (optional): Gender focus ("male", "female", or "both")
- `customer_review` (optional): Customer testimonial or quote (max 5000 chars)

**Example:**
```
Prompt: "Create a customer persona for my business coaching service"

AI client calls customer_persona with details about your business.

Returns a detailed persona with:
- Name and demographics
- Key struggles and pain points
- How your solution helps them
- Behavioral characteristics
```

**Best For:**
- Targeting your marketing messages
- Understanding customer motivations
- Creating relevant content
- Product development insights

---

## brand_voice

Analyze your writing to create a brand voice guide for consistent messaging.

**Parameters:**
- `copy_sample` (required): Sample of your writing (50-5000 chars)

**Example:**
```
Prompt: "Analyze this copy and create a brand voice guide for me: 
[paste your website copy or email]"

Returns analysis of:
- Voice characteristics
- Tone attributes
- Style guidelines
- Words/phrases to use or avoid
```

**Best For:**
- Establishing brand consistency
- Training team members on your voice
- Guiding AI content generation
- Refining your messaging

---

## search

Search Enji's blog posts, Q&A library, and help center for relevant content.

**Parameters:**
- `query` (required): Search terms
- `top_k` (optional): Maximum results (1-20, default: 6)

**Example:**
```
Prompt: "Find Enji content about Instagram marketing strategies"

Returns relevant articles with:
- Document ID
- Title
- URL
```

**Best For:**
- Finding specific Enji resources
- Deep research on marketing topics
- Getting article recommendations
- Exploring Enji's knowledge base

---

## list_resources

Get a list of all available Enji resources and free marketing tools.

**Parameters:**
None required.

**Example:**
```
Prompt: "What free marketing tools does Enji offer?"

Returns:
- Blog
- Q&A Library
- Help Center
- Brand Voice Generator
- Customer Persona Generator
- Blog Idea Generator
- Social Media Idea Generator
- Social Media Scheduler
```

**Best For:**
- Discovering Enji's capabilities
- Finding free marketing tools
- Exploring additional resources
- Getting started with Enji

---

## Combining Tools

You can ask your AI client to use multiple tools in sequence:

**Example Workflow:**
```
Prompt: "Help me create a complete content strategy for my fitness coaching business"

AI client might:
1. Use answer_question to understand fitness marketing best practices
2. Use customer_persona to build your ideal client profile
3. Use blog_ideas to generate blog topics
4. Use social_media_ideas to create social content ideas
```

---

**Need more help?** Visit [enji.co/ai-marketing-agent](https://www.enji.co/ai-marketing-agent)
