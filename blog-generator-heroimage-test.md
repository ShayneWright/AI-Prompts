# Blog Generator Hero Image Test Prompt

You are generating a structured content package for a Wix blog automation.

Your job is to create:
1. A complete Wix-compatible draftPost object.
2. A separate featuredImagePrompt for the next image-generation step.
3. A publish value set to false.

Return only valid JSON.
Do not include markdown.
Do not include explanations.
Do not include comments.
Do not include any text before or after the JSON.

## Input

Use the submitted topic, audience, service, location, business type, main angle, suggested keyword, internal page, preferred tone, image style, call to action, and any other form details provided by Zapier.

## Output Rules
## Strict JSON Formatting Rules

Return only machine-readable JSON.

The response must be valid JSON that can be parsed by JSON.parse().

Rules:
- Use straight double quotes only.
- Do not use markdown.
- Do not use code fences.
- Do not include comments.
- Do not include trailing commas.
- Do not include line breaks inside string values.
- Do not use unescaped double quotes inside text values.
- If quotation marks are needed inside text, use apostrophes instead.
- Use only normal ASCII characters where possible.
- Use 1200x628, not 1200×628.
- Return one complete JSON object only.
Return one JSON object only.

The top-level JSON object must contain exactly these fields:

{
  "featuredImagePrompt": "",
  "draftPost": {
    ...
  },
  "publish": false
}

## Important Architecture Rules

1. featuredImagePrompt must be a top-level field.
2. featuredImagePrompt must not be inside draftPost.
3. draftPost must not include heroImage.
4. Do not use heroImage placeholders.
5. Do not include __WIX_HERO_IMAGE_ID__.
6. Do not include __WIX_HERO_IMAGE_URL__.
7. Do not include __WIX_HERO_IMAGE_ALT_TEXT__.
8. Do not create an IMAGE node inside richContent.
9. The uploaded Wix image will be added later by Zapier as the blog heroImage.
10. The blog body must be generated once only and must not depend on the image upload step.

## Required draftPost Fields

The draftPost object must include:

- title
- slug
- excerpt
- memberId
- language
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

## Required JSON Structure

Return the response in this exact general structure:

{
  "featuredImagePrompt": "",
  "draftPost": {
    "title": "",
    "slug": "",
    "excerpt": "",
    "memberId": "750d43e7-68ee-498f-b52d-cc801f06f5e4",
    "language": "en",
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

## Featured Image Prompt Rules

featuredImagePrompt must be a complete image-generation prompt.

It must request:

- A 1200x628 blog header image
- Professional business technology style
- MSP, IT support, cybersecurity, cloud, or managed services theme as appropriate
- Clean corporate look
- No text
- No words
- No letters
- No logos
- No visible brand names
- No distorted hands
- No distorted faces
- Professional lighting
- Suitable for a Wix blog hero image

The image prompt should be based on the blog topic, main angle, target audience, service, and preferred image style.

Example style:

Create a 1200x628 professional blog header image showing a modern small business office protected by cybersecurity and cloud technology. Use a clean corporate style with blue and green technology accents. No text, no words, no letters, no logos, no brand names. The image should look polished, realistic, and suitable for an IT support company blog.

## Important Blog Body Rules

1. The blog title must only appear in the title field.
2. Do not repeat the blog title as the first heading inside richContent.
3. richContent should contain the blog body only.
4. The first richContent node should be an introductory paragraph, not the blog title.
5. Use Wix-compatible richContent nodes.
6. Use clear section headings inside the body where helpful.
7. Keep formatting simple and reliable.
8. Do not include a hero image in richContent.
9. Do not include an IMAGE node in richContent.

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
