---
name: punjabi-helper
description: Punjabi word substitution and language quality skill. 
---

# Punjabi helper Skill

This skill ensures high-quality, authentic Punjabi by replacing anglicized, 
transliterated, or incorrect words with their preferred Punjabi equivalents.

## ALWAYS DO THIS FIRST

Before writing or editing any Punjabi text, read the helper reference:
👉 `C:\Users\inder\.claude\skills\punjabi-helper\references\helper.md`

This file contains the full substitution table, organized by category.

---

## CORE RULES

### 1. Apply substitutions (longest match first)
When producing Punjabi text, check every word/phrase against the helper.
Replace any match with the preferred term. Apply **multi-word phrases before
single words** — e.g. match "ਇੰਟਰੈਸਟ ਰੇਟ" → "ਵਿਆਜ ਦਰ" before trying
"ਰੇਟ" → "ਦਰ" separately.

### 2. Remove phrases with blank replacements
Some helper entries have an empty replacement — this means **delete the
phrase entirely**. Common examples: greetings like "ਸਤਿ ਸ੍ਰੀ ਅਕਾਲ ਜੀ।",
filler phrases like "ਅੱਜ ਦੀ ਖ਼ਬਰ ਇਹ ਹੈ ਕਿ".

### 3. Preserve proper nouns and kept terms
Some entries map to themselves (e.g. ਕੰਪਨੀ → ਕੰਪਨੀ) or to Roman script
(ਗੂਗਲ → Google, ਡਾਓ → DOW). Respect these exactly.

### 4. Keep surrounding grammar intact
When substituting, ensure the rest of the sentence remains grammatically
correct in Punjabi. Adjust case endings or verb agreements if needed.

### 5. Expand the helper when asked
If the user says "add this word" or "remember this correction", update
`C:\Users\inder\.claude\skills\punjabi-helper\references\helper.md`
by appending the new pair to the correct category table. Confirm the addition to the user.

---

## ADDING NEW WORDS

When the user wants to add a new substitution, ask for:
- The **incorrect/anglicized** form (what to replace)
- The **preferred Punjabi** form (what to use instead)
- The **category** (or suggest the best fitting one)

Then append to the correct section in `C:\Users\inder\.claude\skills\punjabi-helper\references\helper.md`.

Example user prompt: *"Add: ਬੈਂਕ → ਬੈਂਕ (keep as is)"* or *"ਚੇਅਰਪਰਸਨ should become ਚੇਅਰਪਰਸਨ"*

---

## WORKFLOW FOR EDITING PUNJABI TEXT

1. **Read** `C:\Users\inder\.claude\skills\punjabi-helper\references\helper.md`
2. **Scan** the input text for any helper key (longest matches first)
3. **Replace** each match with the preferred value
4. **Delete** any phrase whose replacement is empty
5. **Review** the result for natural Punjabi grammar flow
6. **Return** the corrected text

---

## WORKFLOW FOR WRITING ORIGINAL PUNJABI TEXT

1. **Read** `C:\Users\inder\.claude\skills\punjabi-helper\references\helper.md`
2. **Draft** the text in Punjabi
3. **Self-check**: does any drafted phrase appear as a helper key? If so, use the preferred word directly
4. **Return** clean text using only approved vocabulary

---

## NOTES

- The helper is the single source of truth. If a word is not in the
  helper, use your best judgment for authentic Punjabi.
- Prefer Punjabi words over English loanwords whenever a Punjabi equivalent exists.
- For financial/news content specifically, always prefer Punjabi market
  vocabulary (ਬਜ਼ਾਰ not ਮਾਰਕੀਟ, ਨਿਵੇਸ਼ not ਇਨਵੈਸਟਮੈਂਟ, etc.)
