---
name: punjabi-video-script-converter
description: >
  End-to-end pipeline for preparing Punjabi AI learning video scripts.
  Use this skill whenever the user wants to process a script from an existing Punjabi Gurmukhi raw script file,
  Trigger whenever the user mentions: "convert punjabi script", "create scene by scene video script", "Punjabi video",
  "learning video script", , "video script pipeline", or anything that
  involves taking a raw PUNJABI TXT script and producing a Punjabi structured Scene by Scene version for AI video.
  Always use this skill for the full pipeline (Punjabi script conversion),
---
 
# Punjabi AI Video Script Converter
 
Single pipeline that takes a raw PUNJABI TXT script , polishes it into
broadcast-quality content, then converts it to scene by scene ready
for AI video generation.
 
---

### Step 1 — AI Video Flow Review
 
Review the Punjabi script against this checklist:
 
| Check | What to Look For |
|---|---|
| **Sentence length** | Sentences should be speakable in one breath (≤ 20 words). Split longer ones. |
| **Rhythm** | Read aloud mentally. Flag any sentence that sounds stilted or awkward. |
| **Pause markers** | Ensure `...` and `—` translated correctly and still make sense in Punjabi flow |
| **Terminology consistency** | Same concept should use the same Punjabi word throughout |
| **Filler naturalness** | Fillers must feel natural for a Punjabi speaker, not translated robotically |
| **Energy match** | Excited English = excited Punjabi. Don't flatten the tone. |
| **Cultural fit** | American examples should be preserved (don't re-Indianize them) but explained if culturally distant |
| **Completeness** | No English sentences left untranslated; no sections skipped |
 
If issues are found, fix them inline — do not flag and move on.
 
---
 
## Step 2 — YouTube Scene-by-Scene Video Script
 
> **Prerequisite:** flow review must be complete.
> This phase restructures the reviewed Punjabi text into a production-ready YouTube scene script
> **before** writing to the output file. No video is generated — only the script document.
> **Load the YouTube policy reference file** before proceeding:
> `references/youtube-policy.md`
 
### Step 2.1 — YouTube Policy Pre-Check
 
Before structuring scenes, scan the full Punjabi text for any content that would violate
YouTube's Community Guidelines. Refer to `references/youtube-policy.md` for the full rules.
 
Quick-reference flags — REMOVE or REWRITE any content that:
- Depicts or glorifies violence, abuse, or self-harm
- Contains hate speech targeting religion, caste, ethnicity, gender, or nationality
- Makes false health/medical claims presented as facts
- Shows or describes dangerous activities without appropriate safety context
- Contains sexually suggestive language (especially if audience is minors)
- Uses third-party copyrighted material (song lyrics, branded jingles, film dialogue)
- Makes defamatory statements about real individuals or organizations
- Promotes gambling, alcohol, tobacco, or restricted financial products
If violations are found: rewrite the offending content to preserve the educational intent
while complying with policy. Note each change with an inline comment:
`[YT-POLICY: <brief reason for change>]`
 
### Step 2.2 — Scene Segmentation Rules
 
Divide the reviewed Punjabi script into scenes. Each scene must:
 
- Cover **one complete idea, concept, or teaching point** — do not split mid-thought
- Be **speakable in 20–45 seconds** of voiceover (roughly 60–120 Punjabi words)
- Flow naturally into the next scene — the last sentence of a scene should create a soft
  bridge or curiosity hook into the next
- Be numbered sequentially: `SCENE 01`, `SCENE 02`, etc.
**Mandatory scene structure:**
 
```
SCENE [NN] — [SHORT SCENE TITLE IN PUNJABI]
═══════════════════════════════════════════
 
[VOICEOVER]
[Full Punjabi Gurmukhi narration text for this scene]
 
[CAPTION]
[Punjabi Gurmukhi caption — 1–2 lines max, ≤ 80 characters per line]
[Appears as on-screen subtitle synchronized with voiceover]
 
─────────────────────────────────────────
```
 
### Step 2.3 — Scene Title Rules
 
- Scene title must be in **Punjabi Gurmukhi**
- Titles are descriptive, not clever — they label the concept, e.g.:
  - ✅ `ਜਾਣ-ਪਛਾਣ` (Introduction)
  - ✅ `ਮੁੱਖ ਧਾਰਨਾ` (Main Concept)
  - ✅ `ਉਦਾਹਰਣ` (Example)
  - ✅ `ਸਾਰ ਅਤੇ ਵਿਦਾਈ` (Summary and Goodbye)
- Do NOT use English words in scene titles

### Step 2.4 — Caption Guidelines
 
Captions are the **on-screen subtitle text** synchronized with the voiceover. Rules:
 
- Written in **Punjabi Gurmukhi only**
- Maximum **2 lines per caption block**; maximum **80 characters per line**
- Must be a **condensed version** of the voiceover — the key phrase, not a full sentence repeat
- Use caption to reinforce the single most important word or phrase of the scene
- Do NOT use captions to introduce new information not present in the voiceover
- Captions must comply with YouTube's subtitle/closed-caption policies (no profanity, no hate speech)
### Step 2.5 — Required Scene Types
 
Every video script must contain these scene types (in order):
 
| Scene Type | Position | Purpose |
|---|---|---|
| **Hook / Intro** | Scene 01 | Grab attention; introduce the topic; tease what will be learned |
| **Content Scenes** | Scenes 02–N-1 | One concept per scene; examples embedded naturally |
| **Summary** | Second-to-last scene | Recap the 2–3 most important points from the video |
| **Call to Action (CTA)** | Final scene | YouTube-compliant CTA — see Step 3.7 |
 
### Step 2.6 — YouTube-Compliant Call to Action
 
The final scene CTA must follow YouTube's policies. Permitted CTAs:
 
- ✅ Ask viewers to **like** the video if they found it helpful
- ✅ Ask viewers to **subscribe** to the channel for more videos
- ✅ Ask viewers to **leave a comment** with a question or feedback
- ✅ Direct viewers to **another video or playlist** on the channel
- ✅ Ask viewers to **share** the video with someone who might benefit
Prohibited in CTAs:
- ❌ Promising rewards for likes/subscribes (sub4sub, giveaway manipulation)
- ❌ Directing viewers to external sites that bypass YouTube
- ❌ Countdown pressure tactics ("subscribe in the next 10 seconds")
- ❌ Misleading claims about video content to drive engagement
**CTA template (adapt to Punjabi):**
 
```
ਜੇ ਇਹ ਵੀਡੀਓ ਤੁਹਾਨੂੰ ਪਸੰਦ ਆਈ, ਤਾਂ ਲਾਈਕ ਬਟਨ ਦਬਾਓ ਅਤੇ ਸਾਡੇ ਚੈਨਲ ਨੂੰ ਸਬਸਕ੍ਰਾਈਬ ਕਰੋ।
ਹੋਰ ਸਿੱਖਣ ਲਈ ਅਗਲੀ ਵੀਡੀਓ ਜ਼ਰੂਰ ਦੇਖੋ!
```
 
### Step 2.7 — Final Script File Format
 
The output file written to `Finished/Punjabi/<name>_punjabi.txt` must follow this exact structure:
 
```
════════════════════════════════════════════════
VIDEO SCRIPT: [TOPIC TITLE IN PUNJABI]
LANGUAGE: ਪੰਜਾਬੀ (Gurmukhi)
TOTAL SCENES: [N]
════════════════════════════════════════════════
 
SCENE 01 — [TITLE]
═══════════════════════════════════════════════
 
[VOICEOVER]
...
 
[CAPTION]
...
 
─────────────────────────────────────────
 
SCENE 02 — [TITLE]
...
 
════════════════════════════════════════════════
END OF SCRIPT
════════════════════════════════════════════════
```
 
- Encoding: **UTF-8** (mandatory for Gurmukhi)
- No HTML, no Markdown formatting inside the file — plain text only
- Scene description block always in **English**
- Voiceover and Caption always in **Punjabi Gurmukhi**
---
 
## SUMMARY CHECKLIST
 
After completing all phases, confirm all items:
 
- [ ] Phase 1: Grammar and American English errors corrected
- [ ] Phase 1: Indian cartoon characters replaced with Americanized examples
- [ ] Phase 1: Examples improved for context and flow
- [ ] Phase 1: Punctuation corrected; fillers added for AI voiceover
- [ ] Phase 1: Saved to `Finished/English/<name>_eng_transcribe.txt`
- [ ] Phase 2: Translated to authentic Punjabi Gurmukhi
- [ ] Phase 2: Punjabi dictionary substitutions applied
- [ ] Phase 2: AI video flow reviewed and issues corrected
- [ ] Phase 3: YouTube policy pre-check completed; violations rewritten
- [ ] Phase 3: Script divided into scenes (Hook → Content → Summary → CTA)
- [ ] Phase 3: Each scene has Description (English), Voiceover (Punjabi), and Caption (Punjabi)
- [ ] Phase 3: CTA scene is YouTube-policy compliant
- [ ] Phase 3: Saved to `Finished/Punjabi/<name>_punjabi.txt` in scene script format
Report the output file paths and total scene count to the user when done.
 
---
 
## ERROR HANDLING
 
| Situation | Action |
|---|---|
| Multiple `.txt` files in folder | List them and ask which to process |
| File is empty | Report to user; do not proceed |
| Punjabi dictionary skill not found | Attempt basic translation, flag that substitution quality may be reduced, ask user to install the skill |
| `Finished/` subdirectories don't exist | Create them silently with `mkdir -p` |
| YouTube policy violation found in script | Rewrite offending content, tag with `[YT-POLICY: reason]`, continue processing |
| Scene would exceed 45-second threshold | Split into two scenes at the nearest natural sentence break |
| Script is too short to segment (< 3 logical ideas) | Treat entire script as content scenes; still add Hook and CTA wrappers |
 
---
 
## NOTES FOR FUTURE IMPROVEMENTS
 
- If a style guide file is placed at `references/style-guide.md`, load it during Phase 1 to apply
  project-specific voice/tone rules.
- If an `american-examples.md` reference file exists at `references/american-examples.md`, consult
  it for pre-approved example substitutions before generating new ones.
- Scene timing estimates can be refined by placing a `references/timing-guide.md` with
  words-per-minute data for the specific AI voiceover engine being used.
- Channel-specific CTA wording can be stored in `references/cta-templates.md` to ensure
  consistent branding across all video scripts.