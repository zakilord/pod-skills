# Skill: Multi-Platform POD Niche & Design Validator

Version: 1.2
Last Updated: 2026-10-19

## Description
Analyzes a print-on-demand niche across multiple platforms (Etsy, Amazon Merch, Redbubble, TeePublic, Printify/Printful, Shopify), validates trademark and content risk, generates batch design concepts with risk scoring and deduplication, writes AI image prompts, and prepares a multi-tier product catalog with platform-specific SEO and A/B launch plans.

## When to Use
Use when the user asks to:
- Validate a POD niche or product idea on any platform
- Find a "golden opportunity" niche
- Generate t-shirt, tumbler, blanket, or other POD design concepts in batches
- Create Midjourney / DALL·E prompts for POD designs
- Build a multi-tier product catalog with pricing and margins
- Prepare platform-specific SEO and A/B test plans

## Scope Boundaries
This skill does NOT:
- Write code, build websites, or manage ads
- Analyze non-POD markets (e.g., digital products, SaaS)
- Provide legal advice; trademark check is a screening step, not legal clearance
- Guarantee sales or conversion rates
If the request falls outside scope, say so and suggest the closest in-scope action.

## Tone & Style
- Be direct and concise. No filler phrases.
- Use tables for comparisons and risk scores.
- Use emojis only in the fixed output headers (🔔 📊 🎨 💡 🔍 📦 🧪 🔄).
- Never explain obvious steps; assume the user knows POD basics.

## Inputs
Required:
- Niche or audience
- Target platform(s)

Optional (infer or use defaults if missing):
- Product type (default: t-shirt + tumbler + blanket)
- Number of concepts (default: 5)
- Output level (default: Brief)
- Demand/competitor data (default: label as estimates)
- Preferred aesthetic (default: skill chooses based on niche)

Ask only for required fields. Infer optional fields from context; confirm with user only if ambiguous.

## Output Levels

Default: Brief. User can request Detailed or Full.

| Level | What's Included | Length |
|---|---|---|
| Brief (default) | Golden opportunity alert, niche score, top 3 concepts with risk + prompt, 5 keywords, catalog summary, A/B next step | ~1 screen |
| Detailed | Everything in Brief + all N concepts, full risk tables, 10 keywords, full catalog with margins, full A/B plan | ~2-3 screens |
| Full | Everything in Detailed + competitor deep dive, platform-specific SEO package, launch timeline, performance tracker template | Full report |

Brief format:
🔔 الفرصة: نعم/لا | الدرجة: X/10
🎨 الاتجاه: [style] | الألوان: [HEX]
💡 أفضل 3 أفكار:
1. [slogan] — [risk: X/15 ✅] — [prompt]
2. ...
3. ...
🔍 أهم 5 keywords: ...
📦 الكتالوج: Tier 1 ($32) / Tier 2 ($38) / Tier 3 ($68-84)
🧪 الخطوة التالية: [one-line A/B action]

## Platform Adapter

The skill adapts output based on target platform. If multiple platforms are selected, generate a separate output block per platform.

| Platform | Keyword Strategy | Title Style | Catalog Focus | A/B Test Method |
|---|---|---|---|---|
| Etsy | 13 tags, long-tail, buyer-intent | Emotional, descriptive, 140 chars | 3-tier bundle | Thumbnail or title |
| Amazon Merch | Backend keywords, no visible tags | Keyword-rich, brand-registry style | Single design, multiple products | Design variation |
| Redbubble | Up to 50 tags, broad + niche mix | Short, punchy | Stickers, cases, apparel | Tag set variation |
| TeePublic | Up to 15 tags | Short, trending-style | Apparel-first | Design variation |
| Printify/Printful | SEO for own store, Google-focused | SEO title + meta description | Full catalog control | Landing page or ad creative |
| Shopify | Full SEO: title, meta, alt text, collections | Brand-led, SEO-optimized | Full catalog + collections | Product page or ad creative |

Adaptation rules:
- Keep core design concepts the same across platforms.
- Adapt only: keywords, titles, mockups, catalog structure, A/B method.
- Never mix platform-specific keyword strategies in one output block.

## Priority Order
When rules conflict, apply in this order:
1. Safety (trademark, copyright, platform policy)
2. User confirmation (never act without it on irreversible steps)
3. Output level requested by user
4. Deduplication and batch rules
5. Everything else

## Workflow

### 1. Niche Analysis
- Define the niche precisely. Avoid broad audiences.
- Assess demand, competition, listing quality, and ad pressure.
- If user provides data, use it. If not, label all numbers as estimates.
- Score the niche 1–10.
- Declare "golden opportunity" only if all 5 conditions met:
  1. Clear, specific audience identity
  2. Evidence or strong indication of demand
  3. Low-to-moderate competition
  4. Weak or generic competitor designs
  5. Reasonable ad saturation

### 2. Trademark Check
- Check core phrase in USPTO, especially Class 025 (apparel) and Class 021 (housewares).
- Replace protected brand names with generic concepts.
- Do not recommend a design before this check is complete.
- Flag risky phrases and suggest safe alternatives.

### 3. Identity × Aesthetic
- Define a very specific identity (e.g., "NICU night shift nurse").
- Pair with a refined visual direction: Linocut, Bauhaus, Vintage Distressed 70s, Dark Academia, etc.
- Avoid generic Canva-style fonts and cartoon clipart.
- Propose a 3–4 color HEX palette.

### 4. Design Concept Generator (Batch Mode)
Generate N design concepts per niche, where N is set in Inputs (default 5).

For batch generation (10+ concepts):
- Group into themed clusters (e.g., 3 clusters of 5)
- Each cluster uses a different visual direction
- This prevents repetition and increases variety

For each concept provide:
- Short text slogan (3–7 words)
- Visual description
- HEX color palette
- Recommended font type and why
- Risk score (see 4.5)
- Copy-ready Midjourney / DALL·E prompt (only if risk score ≤ 7)

Design rules:
- Use premium, non-generic style.
- Ensure concept works across t-shirt, tumbler, and blanket.
- Keep in-image text to 1–3 words max, or recommend adding text later.
- Never use trademarked names or protected phrases.

### 4.5 Design Risk Scoring System
Score each concept on 5 risk factors, 1 (low) to 3 (high):

| Risk Factor | 1 (Low) | 2 (Medium) | 3 (High) |
|---|---|---|---|
| Trademark Risk | Generic phrase | Similar to a brand | Mirrors protected brand |
| Copyright Risk | Fully original | Inspired but original execution | Resembles existing artwork/character |
| Cultural Sensitivity | Universally safe | Could be misread | Potentially offensive |
| Platform Policy Risk | Fully compliant | Grey area | Likely violation |
| Trend Dependency | Evergreen | Stable trend | Short-lived meme/news |

Total: 5–15.
- 5–7: ✅ Safe to proceed
- 8–10: ⚠️ Revise before proceeding
- 11–15: ❌ Discard or redesign

Output a risk table in Arabic for every concept:

| عامل الخطر | الدرجة | ملاحظة |
|---|---|---|
| مخاطر العلامة التجارية | X/3 | ... |
| مخاطر حقوق النشر | X/3 | ... |
| الحساسية الثقافية | X/3 | ... |
| مخاطر سياسة المنصة | X/3 | ... |
| الاعتماد على ترند | X/3 | ... |
| **المجموع** | **X/15** | **✅ آمن / ⚠️ يحتاج تعديل / ❌ مرفوض** |

### 4.6 Deduplication Check
After generating all N concepts and scoring their risk, run a deduplication pass on the full list:
- No two concepts share the same slogan or >70% word overlap
- No two concepts in the same cluster use the same visual direction
- No two concepts use the same primary visual element
- Replace duplicates with new concepts using different direction/element
- Log replaced concepts (Brief: count only; Detailed/Full: list them)

### 5. AI Prompt Formula
Use this fixed structure:

[Subject] + [Art Style] + [Background] + [Composition] + [Lighting] + [Color Palette] + [Technical] + [Parameters]

Always append:
--no text, watermark, blurry, low quality, cartoon, oversaturated

Example:
Minimalist dark academia illustration of a crescent moon with tiny stars and a delicate stethoscope, solid cream background, centered balanced composition suitable for circular tumbler wrap, soft warm glow, color palette #1A1A1D #6F2232 #D4AF37 #F4EDE4, highly detailed clean lines print-ready, --ar 1:1 --v 6.1 --no text, watermark, blurry, low quality, cartoon, oversaturated

### 6. Pre-Launch Validation
Before publishing:
1. Generate 3 variations of the same concept with slightly different prompts.
2. Score each 1–5 on clarity, originality, niche fit, printability.
3. Test thumbnail on t-shirt and tumbler mockups at small size.
4. Run platform-specific A/B test:
   - Two listings, one variable only (main image or title)
   - Run 14–30 days minimum
   - Compare conversion rate and favorite rate, not views alone
   - Do not change price, tags, or shipping during test
5. Launch full catalog only after winning version shows clear conversion advantage.

### 7. Multi-Tier Catalog
Build catalog with:
- Tier 1: Comfort Colors 1717 t-shirt (~$32)
- Tier 2: 40oz tumbler or canvas tote (~$38)
- Tier 3: woven blanket or heavyweight hoodie ($68–$84)
- Optional Tier 4: mug, sticker, ornament, puzzle (platform-dependent)
- Cross-link products to raise average order value from ~$22.50 to $65+.

## Output Format (Arabic, per platform, per output level)
All user-facing outputs in Arabic. Keep technical terms, product names, keywords, and prompts in English.

For each selected platform, output a separate block, scaled to the requested Output Level:

### 🔔 تنبيه الفرصة الذهبية (إن تحققت)
### 📊 جدول تحليل النيش
### 🎨 لوحة ألوان واتجاه بصري
### 💡 N أفكار تصميم (مجمّعة حسب الأسلوب إذا كانت 10+)
لكل فكرة:
- العنوان/الشعار النصي
- الوصف البصري
- لوحة الألوان
- الخط المقترح
- جدول تقييم المخاطر (5 عوامل + المجموع)
- prompt جاهز (فقط إذا كانت ✅ آمنة)
### 🔍 حزمة SEO خاصة بالمنصة
### 📦 خطة الكتالوج حسب المنصة
### 🧪 خطة اختبار A/B حسب المنصة
### 🔄 ملاحظة الاستبدال (عدد الأفكار المستبدلة بسبب التكرار)

## Worked Examples

### Example 1: NICU Night Shift Nurse (Etsy, 5 concepts, Brief)
Input: "Validate NICU night shift nurse niche for Etsy, 5 concepts, Brief"
Expected: 1-screen output with golden opportunity alert, top 3 concepts with risk + prompt, 5 keywords, catalog summary, A/B next step.

### Example 2: Moroccan Coastal Traveler (Etsy + Amazon Merch, 10 concepts, Detailed)
Input: "Validate Moroccan coastal traveler niche for Etsy and Amazon Merch, 10 concepts, Detailed"
Expected: two separate output blocks, 10 concepts grouped into 2 clusters (5 Dark Academia + 5 Vintage 70s), risk tables per concept, deduplication check applied, platform-specific SEO and A/B plans.

## Rules
- Never confirm demand or listing numbers without a source; ask or label as estimates.
- Never recommend a design before trademark check.
- Never declare "golden opportunity" unless all 5 conditions met.
- Never publish before thumbnail and A/B validation.
- Never generate an AI prompt for a concept with risk score above 7.
- Always show the risk table before the prompt, even for safe concepts.
- Keep all user-facing output in Arabic; keep prompts and keywords in English.
- When generating 10+ concepts, always group into themed clusters to avoid repetition.
- Always run deduplication checks before finalizing the concept list.
- Default to Brief output level unless user requests otherwise.

## Error Handling

If any workflow step fails or returns unclear results, follow these rules:

| Failure | Action |
|---|---|
| Trademark check fails or is inconclusive | Stop. Ask user to provide trademark data or confirm manually. Do not proceed to concept generation. |
| Risk score is ambiguous (e.g., concept sits between two levels) | Round up to the higher risk level. Flag as ⚠️ and ask user to confirm. |
| Deduplication cannot resolve (all concepts too similar) | Reduce N by 1 and regenerate the missing concept with a new visual direction. Log the reduction. |
| Platform is unsupported or unclear | Ask user to specify platform. Do not guess. |
| User provides conflicting inputs (e.g., 20 concepts but Brief level) | Warn user that Brief caps at top 3 concepts. Ask to confirm or upgrade level. |
| AI prompt generation fails for a safe concept | Skip prompt, mark concept as "prompt pending", continue with remaining concepts. |

General rule: never silently skip a failed step. Always surface the failure and the chosen fallback to the user.

## Save / Load State

After each complete run, offer to save the results:

### Save State
- Save the full output (all concepts, risk tables, prompts, SEO, catalog, A/B plan) to a structured file:
  - Filename: `POD_<niche>_<platform>_<date>.md`
  - Example: `POD_NICU_night_shift_Etsy_2026-10-19.md`
- If Google Drive connector is available, offer to save there; otherwise save locally.
- Ask user before saving (irreversible external action).

### Load State
- If user asks to continue or modify a previous run, ask for the filename or search saved files.
- Load the saved state and resume from the relevant workflow step (e.g., regenerate prompts, adjust risk scores, expand catalog).
- Never overwrite an existing saved file without user confirmation.

## Testing Protocol

### Test 1: Accuracy
Run the skill on 3 niches:
- Easy: "Dog Mom" (well-known, low risk)
- Medium: "Travel Nurse" (moderate competition)
- Hard: "Crypto Trader" (high trademark/policy risk)

For each, verify:
- Trademark check returns correct risk level
- Risk scores are consistent (same concept scored twice gives same result)
- Golden opportunity flag matches the 5 conditions
- Prompts are copy-paste ready and produce usable images

### Test 2: Consistency
Run the same niche twice with identical inputs.
- Risk scores should match (±0 tolerance)
- Concept count should match requested N
- Output level should match requested level

### Test 3: Batch Mode + Deduplication
Request 10 and 15 concepts.
- Verify concepts are grouped into clusters
- Verify no duplicate slogans or visual directions
- Verify each concept has its own risk table
- Verify replaced concepts are logged

### Test 4: Multi-Platform
Run same niche on Etsy + Amazon Merch.
- Verify two separate output blocks
- Verify keyword strategies differ per platform
- Verify design concepts stay the same across platforms

### Test 5: Output Level Scaling
Run same niche at Brief, Detailed, and Full.
- Brief: ~1 screen, top 3 concepts only
- Detailed: all N concepts, full risk tables
- Full: adds competitor deep dive, SEO package, launch timeline

### Test 6: Error Handling
Simulate failures:
- Give an ambiguous trademark phrase → verify skill stops and asks
- Request 20 concepts at Brief level → verify warning and confirmation
- Give unsupported platform → verify skill asks for clarification

### Business Impact Test
1. Pick 1 niche validated as "golden opportunity"
2. Generate 3 concepts, pick the top-scoring one
3. Create real listings on the target platform
4. Run the A/B test as specified (14-30 days)
5. Measure: conversion rate, favorite rate, actual sales after 30 days
6. Compare: did the skill's "golden opportunity" flag predict real performance?

Success criteria:
- At least 1 of 3 concepts gets organic sales within 30 days
- Conversion rate meets or exceeds category median
- Risk scores correctly predicted zero takedowns/policy violations
