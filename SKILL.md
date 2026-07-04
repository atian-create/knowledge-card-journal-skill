---
name: knowledge-card-journal
description: Use when raw notes, screenshots, Xiaohongshu posts, links, or voice transcripts need to be turned into A Tian style beige journal knowledge cards with clear structure, card-ready copy, and next-step publishing directions.
---

# Knowledge Card Journal

## Overview

This skill turns messy content into small, publishable knowledge outputs.
It is not a generic summarizer. It should output either:
- card-ready copy, or
- a dense A Tian hand-account infographic poster structure

The style target is A Tian's beige journal system: calm but clear judgment, cute educational poster feel, strong readability, thick outlined titles, pastel content blocks, and content that can really be laid out later.

Use this skill when the user wants one of these outcomes:
- turn a Xiaohongshu post, note, or screenshots into 3-5 knowledge cards
- turn one idea into A Tian style beige journal card copy
- turn a long piece of knowledge into one dense hand-account infographic poster
- organize content for later posting, saving, or building a personal knowledge base
- convert raw material into a card set instead of a long article

Do not use this skill when the user actually wants:
- a long-form article
- a pure technical summary
- only image generation without card copy
- a generic prompt list with no structured output

## Workflow

### 1. Read the raw material

Acceptable inputs:
- pasted text
- transcript
- OCR text from screenshots
- a content link after the content has been fetched
- scattered user notes

First identify:
- the real topic
- the one core judgment
- 3-5 usable sub-points
- whether the material is better for knowledge cards, emotional cards, or action cards

If the material is weak, say so briefly and tighten the scope instead of faking depth.

### 2. Compress into cards

Each card should do one job only.

Good card traits:
- one short title
- one clear point
- 2-4 short lines of support
- no bloated explanation
- no assistant-sounding filler

Default to 3-5 cards.
Do not output 8-10 cards unless the user explicitly wants a larger set.

### 2B. Or compress into one poster

Use poster mode when the user wants:
- a single Xiaohongshu-ready infographic
- dense educational content on one page
- a result closer to A Tian's old hand-account posters than a multi-card carousel

Poster mode should not be a wall of text.
It should be one clear teaching flow with fixed sections.

### 3. Apply A Tian style

Visual/tone guidance:
- beige journal feeling, not business PPT
- calm, direct, third-person or light editorial phrasing
- short titles
- restrained emotional tone
- useful over pretty
- keep lines short enough to be placeable on a card or poster block later

Poster-specific visual guidance:
- 3:4 vertical poster
- cream paper or notebook background
- thick black outlined main title
- pastel rounded content blocks
- cute sticker-style A Tian mascot
- small icons, stars, arrows, clocks, planets, tape, or notebook doodles
- high information density but still scannable
- top title, middle teaching flow, bottom summary
- each block should teach one clear sub-part

Avoid:
- generic motivational tone
- over-designed copy
- too many buzzwords
- long paragraphs that cannot fit a card
- sounding like "AI summarized this"

### 4. Choose the right ending

The output should end with two things:
- one `一句判断`
- one `下一步建议`

This is the part the user said they may forget. Keep it stable.

Recommended final two lines:
- `一句判断：这组内容更适合被整理成[知识卡/情绪卡/行动卡]，重点不是信息多，而是判断准。`
- `下一步：如果要，我可以继续把这组内容改成小红书发图版、知识库收藏版，或公众号展开版。`

## Output Contract

Default output shape:

### 主题
One line only.

### 核心判断
One short paragraph or 2-3 short lines.

### 卡片 1
`标题`
2-4 short lines.

### 卡片 2
`标题`
2-4 short lines.

### 卡片 3
`标题`
2-4 short lines.

Optional:
- 卡片 4
- 卡片 5

### 风格备注
Brief note for later layout, for example:
- beige journal
- sparse layout
- handwritten emphasis
- one small sticker or underline per card

### 一句判断
One sentence.

### 下一步
Offer exactly 2-3 concrete follow-up formats, not an open-ended brainstorm.

## Poster Template Contract

Use this mode when the user asks for:
- 手帐图
- 海报版
- 3:4 知识图
- 高信息密度发图

Default poster structure:

### 1. 顶部标题区
- one long main title
- one short subtitle
- 3-4 small tags

### 2. 引言区
- one short opening judgment
- one data point, contrast, or pain point

### 3. 主体内容区
- usually 4 blocks
- each block has:
  - one block title
  - 2-4 short bullets
  - one yellow-style highlight sentence or sticker takeaway

### 4. 人物与贴纸区
- A Tian mascot in center or near center
- icons should support the content, not decorate randomly

### 5. 底部总结区
- one short summary title
- one compact wrap-up
- one strong closing line

Important:
- keep each block visually distinct
- do not overfill any single block
- compress wording before adding more sections
- poster mode is structure-first, not paragraph-first

## Testing

Use the smallest possible test first.

### Test 1: Plain text input
Give the skill one short paragraph and check:
- did it find the real topic
- did it compress into 3-5 cards
- are the titles short enough
- does the final `一句判断 + 下一步` appear

### Test 2: Screenshot-like messy input
Give it fragmented text and check:
- did it clean the structure without hallucinating
- did it preserve the useful point
- did it stay card-like instead of article-like

### Test 3: Style check
Read the output and ask:
- does this sound like beige journal cards
- can each card fit on an image
- is it useful enough to save or post

If any test fails, tighten card count, shorten titles, and reduce explanation.

## Reference

For a concrete example input/output pair, read [references/test-case.md](references/test-case.md).
For the fixed infographic layout, read [references/poster-template.md](references/poster-template.md).
