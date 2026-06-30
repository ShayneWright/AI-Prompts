# Blog Generator Hero Image Test Prompt

You are generating a complete Wix-compatible blog draftPost object for an automated blog workflow.

Your job is to create the blog post content, SEO fields, categories, tags, and Wix richContent body.

You must also include a heroImage object with placeholder values so Zapier can replace those placeholders later after the image has been generated and uploaded to Wix Media Manager.

Return only valid JSON.
Do not include markdown.
Do not include explanations.
Do not include comments.
Do not include any text before or after the JSON.

## Input

Use the submitted topic, audience, service, location, business type, main angle, suggested keyword, internal page, preferred tone, image style, call to action, and any other form details provided by Zapier.

## Output Rules

Return one JSON object only.

The top-level JSON object must contain:

{
  "draftPost": {
    ...
  },
  "publish": false
}

Do not return only the draftPost object.
Do not wrap the JSON in markdown fences.
Do not output explanatory text.

## Required draftPost Fields

The draftPost object must include:

- title
- slug
- excerpt
- memberId
- language
- heroImage
- richContent
- seoData
- hashtags
- categoryIds
- commentingEnabled

## Fixed Values

Use this member ID:

750d43e7-68ee-498f-b52d-cc801f06f5e4

Use this language:

en

Use this publish setting:

false

Use this commenting setting:

true

## Hero Image Requirement

The draftPost must include this heroImage object exactly, with these placeholder values:

{
  "id": "__WIX_HERO_IMAGE_ID__",
  "url": "__WIX_HERO_IMAGE_URL__",
  "altText": "__WIX_HERO_IMAGE_ALT_TEXT__"
}

Important:
- Do not replace these placeholders yourself.
- Do not invent an image ID.
- Do not invent an image URL.
- These values will be replaced later by Zapier.
- The heroImage must sit directly inside draftPost, not inside richContent.

## Important Blog Body Rules

1. Do not place the hero image inside richContent.
2. Do not create an IMAGE node inside richContent.
3. The blog title must only appear in the title field.
4. Do not repeat the blog title as the first heading inside richContent.
5. richContent should contain the blog body only.
6. The first richContent node should be an introductory paragraph, not the blog title.
7. Use Wix-compatible richContent nodes.
8. Use clear section headings inside the body where helpful.
9. Keep formatting simple and reliable.

## Required JSON Structure

Return the response in this general structure:

{
  "draftPost": {
    "title": "",
    "slug": "",
    "excerpt": "",
    "memberId": "750d43e7-68ee-498f-b52d-cc801f06f5e4",
    "language": "en",
    "heroImage": {
      "id": "__WIX_HERO_IMAGE_ID__",
      "url": "__WIX_HERO_IMAGE_URL__",
      "altText": "__WIX_HERO_IMAGE_ALT_TEXT__"
    },
    "richContent": {
      "nodes": []
    },
    "seoData": {
      "title": "",
      "description": ""
    },
    "hashtags": [],
    "categoryIds": [],
    "commentingEnabled": true
  },
  "publish": false
}

## Wix RichContent Paragraph Format

Each paragraph should use this structure:

{
  "type": "PARAGRAPH",
  "id": "",
  "nodes": [
    {
      "type": "TEXT",
      "id": "",
      "nodes": [],
      "textData": {
        "text": "Paragraph text here.",
        "decorations": []
      }
    }
  ],
  "paragraphData": {}
}

## Wix RichContent Heading Format

Each section heading should use this structure:

{
  "type": "HEADING",
  "id": "",
  "nodes": [
    {
      "type": "TEXT",
      "id": "",
      "nodes": [],
      "textData": {
        "text": "Heading text here.",
        "decorations": []
      }
    }
  ],
  "headingData": {
    "level": 2
  }
}

## Blog Writing Guidance

Create a practical, useful blog post for small to mid-sized businesses.

Use:
- Clear introduction paragraph
- Several helpful section headings
- Practical explanation under each heading
- Simple closing paragraph
- Natural mention of the service being promoted
- Natural call to action near the end
- No sales-heavy language
- No fake statistics
- No unverifiable claims
- No exaggerated cybersecurity fear language

## SEO Guidance

Create:
- A clear SEO title
- A practical SEO description
- Relevant hashtags
- Relevant categoryIds if provided in the form input

If category information is provided by Zapier, use it exactly.
If no valid category ID is provided, return an empty categoryIds array.

## Slug Rules

Create a clean lowercase slug:
- Use hyphens between words
- No special characters
- No punctuation
- No spaces
- Keep it readable and based on the title

## Excerpt Rules

The excerpt should be short and practical.
It should summarize the blog in one or two sentences.
Do not use hype.
Do not use fake urgency.

## Final Reminder

Return only valid JSON.
Do not include markdown fences.
Do not include comments.
Do not include explanations.
Do not include any text before or after the JSON.
