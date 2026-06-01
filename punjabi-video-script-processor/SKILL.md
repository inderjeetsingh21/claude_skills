---
name: punjabi-video-script-processor
description: >
  End-to-end pipeline for preparing Punjabi AI learning video scripts.
  Use this skill whenever the user wants to process a script from the ReadyToProcess folder,
  polish it in English, then convert it to authentic Punjabi Gurmukhi for AI video generation.
  Trigger whenever the user mentions: "ReadyToProcess", "process the script", "Punjabi video",
  "learning video script", "convert to Punjabi", "video script pipeline", or anything that
  involves taking a raw TXT script and producing both an English and Punjabi version for AI video.
  Always use this skill for the full two-phase pipeline (English polish → Punjabi conversion),
  even if the user only asks for one phase — confirm scope with them first.
---
 
# Punjabi AI Video Script Processor
 
Two-phase pipeline that takes a raw TXT script from `ReadyToProcess/`, polishes it into
broadcast-quality American English, then converts it to authentic Punjabi Gurmukhi ready
for AI video generation.
 
---
 
## PHASE 1 — English Polish
 
### Step 1.1 — Locate and Read the Source File
 
```
ReadyToProcess/          ← source folder
Finished/
  English/               ← Phase 1 output
  Punjabi/               ← Phase 2 output
```
 
1. List all `.txt` files in `ReadyToProcess/`. If multiple files exist, ask the user which one to process.
2. Read the full file content with `view` or `bash_tool` (cat).
3. Note the original filename (without extension) — it becomes the base for all output names.
### Step 1.2 — Grammar & Language Fix (American English)
 
Apply ALL of the following corrections:
 
| Issue | Rule |
|---|---|
| British spellings | Convert to American (colour → color, organise → organize, etc.) |
| Subject-verb agreement | Fix silently |
| Tense consistency | Maintain consistent tense throughout; flag major shifts |
| Article usage (a/an/the) | Fix per American English rules |
| Run-on sentences | Split at natural breath points (useful for AI voiceover pacing) |
| Sentence fragments | Complete them or merge with adjacent sentence |
| Comma splices | Fix with period, semicolon, or conjunction |
| Apostrophes | Fix possessives and contractions |
| Capitalization | Sentence-initial, proper nouns, acronyms |
| Preposition errors | Fix incorrect prepositions |
| Word choice | Replace informal/incorrect words with precise American English equivalents |
| Overall structure | Replace with Americanized writing structure |

 
### Step 1.3 — Replace Indian Cartoon / Non-American Examples
 
Scan for **ANY** examples, analogies, referenses to any characters, person or people.

**REPLACE ALL examples, analogies, referenses** with proper, professional and industry standard explanations.
 
When using an example or analogy use these **criterias:**
- The example or analogy must directly illustrate the concept being taught — not just be a fun name-drop
- Example or analogies should follow a logical progression (simple → complex) matching the script's teaching arc
- If the original example was weak or off-topic, re-write a stronger one with acceptable standard and real world AI examples from well known news articles 
- Keep examples concise — one sentence each unless the concept requires more
- Avoid overusing the character/brand. **Keep** examples professional grade.
- **DO NOT** use any movie character or fictional character in examples.

### Step 1.4 — Punctuation & AI Video Fillers
 
**Punctuation rules for AI voiceover:**
- Use ellipsis `...` for deliberate dramatic pauses (not mid-sentence rambling)
- Use em dash `—` for a sharp pivot or emphasis break
- Use commas liberally at natural breath points
- End all sentences with proper terminal punctuation
- Questions must end with `?`
- Exclamations should be used sparingly but kept where energy is needed
**Fillers — add where beneficial for AI voiceover naturalness:**
 
| Context | Filler to Add |
|---|---|
| Introducing a new concept | "Now," / "Alright," / "So," |
| Transitioning between ideas | "Next up," / "Moving on," / "Here's the thing —" |
| Emphasizing a key point | "And this is important:" / "Remember," |
| Before an example | "For example," / "Think of it this way:" / "Here's a great example:" |
| Wrapping up a section | "Great job!" / "See how that works?" / "Makes sense, right?" |
| Encouraging the viewer | "You've got this!" / "Don't worry, we'll break it down." |
 
> ⚠️ Do NOT add fillers that would sound unnatural or patronizing for the apparent audience level.
> Read the tone of the original script and match it.
### Step 1.5 — Fix the flow of the document
 
- READ the document carefully
- Make sure that the script has a GOOD professional flow
- REPLACE or REMOVE the content which does not make sense with the overall structure
- When REPLACING, make sure to use the content which is industry approved and creates an Impact.
- Carefully analyze the content and see where can we add reference to an ongoing new event. Then, ADD
 
### Step 1.6 — Save English Output
 
- Output path: `Finished/English/<original_filename>_eng_transcribe.txt`
- Create the directory if it doesn't exist
- Encoding: UTF-8
---

*** MOST IMPORTANT *** Take approval before proceeding to PHASE 2
A HUman needs to approve the Output file FIRST.

## PHASE 2 — Punjabi Gurmukhi Conversion
 
> **Prerequisite:** Phase 1 must be complete. Use the `_eng_transcribe.txt` file as input.
> **This phase requires the `punjabi-dictionary` skill** — load it before translating.
 
### Step 2.1 — Load Punjabi Dictionary Skill
 
Open and follow `/mnt/skills/user/punjabi-dictionary/SKILL.md` for all substitution rules.
Detect the domains present in the English script and load the relevant category files.
 
### Step 2.2 — Translate to Punjabi Gurmukhi
 
Translation principles:
 
1. **Translate meaning, not words** — idiomatic, natural Punjabi; not a word-for-word mapping
2. **Gurmukhi script only** — no Romanized Punjabi, no Devanagari
3. **Apply all punjabi-dictionary substitutions** — Punglish/anglicized words must be replaced
4. **Preserve structure** — maintain the same paragraph/section breaks as the English file
5. **Preserve fillers** — translate English fillers to their natural Punjabi equivalents:
   - "Now," → "ਹੁਣ,"
   - "Alright," → "ਚੰਗਾ,"
   - "So," → "ਤਾਂ,"
   - "Remember," → "ਯਾਦ ਰੱਖੋ,"
   - "For example," → "ਉਦਾਹਰਣ ਵਜੋਂ,"
   - "Great job!" → "ਸ਼ਾਬਾਸ਼!"
   - "Makes sense, right?" → "ਸਮਝ ਆਇਆ, ਠੀਕ ਹੈ?"
6. **Numbers** — keep numerals as digits; spell out when used in an explanatory sentence
7. **Proper nouns / brand names** — keep in Roman script embedded within Gurmukhi text
8. **Technical terms with no Punjabi equivalent** — keep English term, add Gurmukhi explanation in parentheses on first use
### Step 2.3 — AI Video Flow Review
 
After translation, review the Punjabi script against this checklist:
 
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
 
## PHASE 3 — YouTube Scene-by-Scene Video Script
 
> **Prerequisite:** Phase 2 translation and flow review must be complete.
> This phase restructures the reviewed Punjabi text into a production-ready YouTube scene script
> **before** writing to the output file. No video is generated — only the script document.
> **Load the YouTube policy reference file** before proceeding:
> `references/youtube-policy.md`
 
### Step 3.1 — YouTube Policy Pre-Check
 
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
 
### Step 3.2 — Scene Segmentation Rules
 
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
 
### Step 3.3 — Scene Title Rules
 
- Scene title must be in **Punjabi Gurmukhi**
- Titles are descriptive, not clever — they label the concept, e.g.:
  - ✅ `ਜਾਣ-ਪਛਾਣ` (Introduction)
  - ✅ `ਮੁੱਖ ਧਾਰਨਾ` (Main Concept)
  - ✅ `ਉਦਾਹਰਣ` (Example)
  - ✅ `ਸਾਰ ਅਤੇ ਵਿਦਾਈ` (Summary and Goodbye)
- Do NOT use English words in scene titles

### Step 3.5 — Caption Guidelines
 
Captions are the **on-screen subtitle text** synchronized with the voiceover. Rules:
 
- Written in **Punjabi Gurmukhi only**
- Maximum **2 lines per caption block**; maximum **80 characters per line**
- Must be a **condensed version** of the voiceover — the key phrase, not a full sentence repeat
- Use caption to reinforce the single most important word or phrase of the scene
- Do NOT use captions to introduce new information not present in the voiceover
- Captions must comply with YouTube's subtitle/closed-caption policies (no profanity, no hate speech)
### Step 3.6 — Required Scene Types
 
Every video script must contain these scene types (in order):
 
| Scene Type | Position | Purpose |
|---|---|---|
| **Hook / Intro** | Scene 01 | Grab attention; introduce the topic; tease what will be learned |
| **Content Scenes** | Scenes 02–N-1 | One concept per scene; examples embedded naturally |
| **Summary** | Second-to-last scene | Recap the 2–3 most important points from the video |
| **Call to Action (CTA)** | Final scene | YouTube-compliant CTA — see Step 3.7 |
 
### Step 3.7 — YouTube-Compliant Call to Action
 
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
 
### Step 3.8 — Final Script File Format
 
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
| `ReadyToProcess/` folder not found | Tell the user the expected path and ask them to confirm the folder location |
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