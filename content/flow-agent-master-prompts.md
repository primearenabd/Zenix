# Zenix Reels: Flow Agent Master Prompts

One prompt per reel. Turn on **Agent** in Flow's prompt box, paste the project instructions once, then paste one reel's master prompt. The Agent plans and generates the three 10-second clips for that reel.
Status: draft. Nothing has been generated or published. Always test on the MAP reel first.

---

## What the research found

**Confirmed by public sources (Google's Flow help pages and third-party write-ups):**
- Agent is a toggle in Flow's prompt box. It is a Gemini-powered planner that can brainstorm, plan storyboards, create multiple variations or assets at once, edit, and organise a project. It remembers the project across steps.
- It can batch: for example "give me 5 variations of this video", or apply one change across many clips.
- Characters stay consistent when you upload reference images and refer to them with @tags. Without @tags, faces drift over a long project.
- Project-level "Agent Instructions" (role, goal, consistency rules) are supported, and the Agent can be told to propose a plan and wait for approval.
- For shots that continue across clips, using the last frame of clip A as the reference for clip B keeps the subject and space continuous.
- Agent chat queries do not cost Flow credits, but there is a daily limit on Agent queries that Google has not published. **The video clips the Agent generates do cost credits.**

**Sources:** [Use the Flow Agent (Google Flow Help)](https://support.google.com/flow/answer/17093911?hl=en), [Create videos in Google Flow (Google Flow Help)](https://support.google.com/flow/answer/16353334?hl=en), [Getting the most out of your agent in Google Flow (Flow on X)](https://x.com/FlowbyGoogle/article/2082926006017630576), [How to Use Google Flow Agent (Medium)](https://medium.com/ai-systems-lab/how-to-use-google-flow-agent-a-step-by-step-guide-0c08f1faf6a7), [Omni Flash pricing (WaveSpeed)](https://wavespeed.ai/blog/posts/omni-flash-pricing/). I could not open the Google pages directly, so their details come from search summaries.

**Not confirmed (check in your Flow screen before relying on it):**
- Whether the Agent can press **Extend** itself. The master prompts tell it to use Extend if it can, and otherwise to chain with the last frame of the previous clip, and to report which it used.
- Whether it generates the three clips in parallel or one after another. One after another keeps the face and voice consistent. Parallel is faster but each clip gets its own voice.
- The size limit of the prompt box. If a master prompt is cut off, paste it in two messages.
- Credit cost. Sources disagree: one says 7 to 15 credits for a 720p clip of 4 to 10 seconds, another says 30 credits for a 10-second 720p clip. At 3 clips a reel, that is roughly 21 to 90 credits per reel, or 210 to 900 for ten. One source says accounts get 50 credits a day by default. **Check your balance and price per clip in Flow before you run more than one reel.**

**What this changes:** one paste per reel instead of three separate generations plus the extend steps. It does not remove the need to check each result, add captions and graphics, and swap the voice if it drifts.

---

## Set up once

**1. Upload reference images** and give each a tag in Flow:
- `@presenter-armchair`: the armchair studio image (cream sweater)
- `@presenter-office`: the office studio image (navy blazer)
- `@presenter-couch`: the couch studio image (brown sweater)
- `@map-frame`: your finished MAP first frame (phone with the CLOSED listing)
- `@grow-megaphone-frame`: your finished GROW megaphone frame

**2. Turn Agent on and paste the project instructions once** (use Flow's Agent Instructions if your screen has it; otherwise paste it as your first message in the project):

```
ROLE: You are the video producer for Zenix, a marketing agency that specialises in supermarkets and grocery stores.
GOAL: Produce vertical 9:16 Instagram reels of about 30 seconds. Each reel is three consecutive 10-second Gemini Omni Flash 1.1 clips with native audio.
CONSISTENCY: The presenter is always the man in the tagged presenter reference. Keep his face, hair, beard, watch, outfit and studio identical in every clip. Tell me if any asset looks off.
VOICE: The same calm, warm, confident adult male voice with dry deadpan delivery in every clip. He speaks the lines exactly as written. Lips match speech. No music.
LOOK: Warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots. Every shot lasts 2 to 4 seconds.
TEXT: Never render readable text, logos, subtitles or watermarks, except what is already inside a first-frame image I supply.
PROPS AND B-ROLL: Plain, unbranded props. B-roll is generic and never presented as a real named store.
WORKFLOW: When I give you a reel, do every step in order without waiting for approval. Chain the clips for continuity: use Extend on the previous clip if you can; otherwise use the last frame of the previous clip as the first frame of the next clip. Finish with a short report: which method you used for each clip, and anything that looks wrong (face, hands, props, lip-sync, voice change). Do not publish anything.
```

**3. Paste one reel's master prompt below.** Generate in this order: MAP, STORE, WEEK, PLAN, PREFLIGHT, PAGE, HOOKS, REPLY, SQUINT, GROW.

**If it goes wrong:** if the Agent ignores the three-clip structure, ask it to "do clip 1 only" and then "extend it with clip 2", and so on. If you want a safer flow, add "Show me the plan and wait for my OK before generating" to the start of any master prompt.

---

# Reel 1: MAP

Studio: armchair. Paste the whole block below into the Agent prompt box.

```
TASK: Make the reel "MAP". It is one 30-second vertical 9:16 video made of three consecutive 10-second Gemini Omni Flash 1.1 clips with native audio. Do all steps in order, then show me the three clips and your report.

PRESENTER: @presenter-armchair is the man. Keep his face, hair, beard, watch, outfit and studio identical in every clip.

STEP 0, FIRST FRAME: I have attached my finished first-frame image as @map-frame (man in the armchair holding a phone with a generic map listing and a red CLOSED label, his other finger pointing at it). Use it exactly as the first frame of clip 1. Do not regenerate it.

STEP 1, CLIP 1 (10 seconds, image-to-video from the first frame):
First frame: the uploaded image. The man sits in a green armchair in front of a chalkboard in a warm study, holding a smartphone at chest height showing a map listing with a red CLOSED label, his other index finger pointing at the screen. Keep the phone screen exactly as in the image and hold the phone still.
0-1.8s SHOT 1 (A-roll, medium shot): deadpan, looking into the lens, he says: "Your store sign says open."
1.8-3.2s SHOT 2 (A-roll, tight close-up on the phone and his pointing finger): he taps the screen twice with his index finger and says: "Google says closed."
3.2-5s SHOT 3 (A-roll, medium shot, slight low angle): he lifts his eyebrows and tilts his head at the phone: "Guess who shoppers believe."
5-7.5s SHOT 4 (B-roll): a shopper glances at a phone outside a storefront, frowns. His voice continues: "Some won't call to check."
7.5-10s SHOT 5 (B-roll): the same shopper turns and walks away down the street at dusk. His voice continues: "They'll just go elsewhere."

STEP 2, CLIP 2 (10 seconds). Continue directly from clip 1: use Extend if you can, otherwise use the last frame of clip 1 as the first frame.
Extend the previous clip by 10 seconds. Same man, same armchair, same voice.
0-4s SHOT 1 (B-roll): a car driving past a warm-lit storefront at dusk, slow tracking shot. His voice continues: "Nearby shoppers can be gone before they ever reach your door."
4-6.5s SHOT 2 (A-roll, medium shot): back to the man, phone lowered, a pen in his hand: "Check today's hours,"
6.5-10s SHOT 3 (B-roll): close-up of a hand ticking items on a blank list beside a generic shop door hours sign, text unreadable. His voice continues: "then weekends and holidays."

STEP 3, CLIP 3 (10 seconds). Continue directly from clip 2 in the same way.
Extend the previous clip by 10 seconds. Same man, same armchair, same voice.
0-4s SHOT 1 (B-roll): a hand holding a phone over a generic business listing, tapping the call, directions and photos icons in turn, all text unreadable. His voice continues: "Test your phone number, directions, and photos on a customer's phone."
4-7s SHOT 2 (A-roll, medium shot): back to the man, straight to camera: "DM the word MAP"
7-10s SHOT 3 (A-roll, close-up): he smiles slightly: "and Zenix will review your local listing." Hold still for the final second.

REPORT: For each clip, say which method you used (Extend or last-frame), and flag anything wrong with the face, hands, props, lip-sync, voice or text.
```

---

# Reel 2: STORE

Studio: office. Paste the whole block below into the Agent prompt box.

```
TASK: Make the reel "STORE". It is one 30-second vertical 9:16 video made of three consecutive 10-second Gemini Omni Flash 1.1 clips with native audio. Do all steps in order, then show me the three clips and your report.

PRESENTER: @presenter-office is the man. Keep his face, hair, beard, watch, outfit and studio identical in every clip.

STEP 0, FIRST FRAME: Generate the first-frame image using @presenter-office as the reference for the man and the studio. Image prompt: Edit the office reference: he sits slightly right of centre with one hand flat on the marble table and the other on the open green folder, which holds one blank white sheet. He leans in slightly and looks straight into the lens, serious and focused. Clean, empty wall to his left. Show it to me, check that the face matches the reference (regenerate once if it does not), then use it as the first frame of clip 1.

STEP 1, CLIP 1 (10 seconds, image-to-video from the first frame):
First frame: the uploaded image. The man sits slightly right of centre at a marble table in a modern office, one hand flat on the table, the other on an open green folder, clean empty wall to his left.
0-2.6s SHOT 1 (A-roll, medium shot): he leans in, looks into the lens, and says: "Four hundred percent. That's not a typo." He taps the table once on "typo" and points to the side.
2.6-5.4s SHOT 2 (A-roll, slow push-in, medium close-up): serious and steady: "Khaamar Baari Supermarket achieved four hundred percent revenue growth"
5.4-8.2s SHOT 3 (A-roll, close-up from a slightly different angle): "in one year while working with Zenix."
8.2-10s SHOT 4 (A-roll, medium shot): he sits back slightly and gives one small nod. No speech.

STEP 2, CLIP 2 (10 seconds). Continue directly from clip 1: use Extend if you can, otherwise use the last frame of clip 1 as the first frame.
Extend the previous clip by 10 seconds. Same man, same office, same voice.
0-3.5s SHOT 1 (A-roll, medium shot): calm and direct: "Specific proof builds trust, and a specific offer does too."
3.5-6.5s SHOT 2 (B-roll): a generic fresh produce display with one clearly highlighted item and a blank price card, slow drift. His voice continues: "Lead with your strongest deal."
6.5-10s SHOT 3 (B-roll): a phone recording a short vertical video of a produce display with a map pin icon in the corner. His voice continues: "Show the price and where to find the store,"

STEP 3, CLIP 3 (10 seconds). Continue directly from clip 2 in the same way.
Extend the previous clip by 10 seconds. Same man, same office, same voice.
0-1.5s SHOT 1 (B-roll): the phone video continues, close-up. His voice continues: "in one short video."
1.5-4.5s SHOT 2 (B-roll): a phone showing a generic business listing with a map pin and opening hours, text unreadable. His voice continues: "Then make sure your Google listing matches."
4.5-7.5s SHOT 3 (A-roll, medium shot): back to the man, hands clasped, straight to camera: "DM the word STORE"
7.5-10s SHOT 4 (A-roll, close-up): calm and inviting: "and Zenix will review your supermarket marketing." Hold still for the final second.

REPORT: For each clip, say which method you used (Extend or last-frame), and flag anything wrong with the face, hands, props, lip-sync, voice or text.
```

---

# Reel 3: WEEK

Studio: armchair. Paste the whole block below into the Agent prompt box.

```
TASK: Make the reel "WEEK". It is one 30-second vertical 9:16 video made of three consecutive 10-second Gemini Omni Flash 1.1 clips with native audio. Do all steps in order, then show me the three clips and your report.

PRESENTER: @presenter-armchair is the man. Keep his face, hair, beard, watch, outfit and studio identical in every clip.

STEP 0, FIRST FRAME: Generate the first-frame image using @presenter-armchair as the reference for the man and the studio. Image prompt: Edit the armchair reference: he sits in the armchair turned slightly toward the chalkboard behind him, a pen in his right hand pointing at the board, looking straight into the lens with a confident, slightly amused expression. No notebook. Show it to me, check that the face matches the reference (regenerate once if it does not), then use it as the first frame of clip 1.

STEP 1, CLIP 1 (10 seconds, image-to-video from the first frame):
First frame: the uploaded image. The man sits in a green armchair in front of a chalkboard, a pen in his hand pointed at the board.
0-3.3s SHOT 1 (A-roll, medium shot): he taps the chalkboard seven times with the pen and says, looking into the lens: "Steal this seven-day content plan for your supermarket."
3.3-5.3s SHOT 2 (B-roll): a hand unpacking fresh produce crates in a bright back room. His voice continues: "Monday, show what just arrived."
5.3-7.3s SHOT 3 (A-roll, close-up): he holds up one finger: "Tuesday, your hero deal."
7.3-10s SHOT 4 (B-roll): a store employee answering a question for a shopper in an aisle, soft focus. His voice continues: "Wednesday, answer a customer question."

STEP 2, CLIP 2 (10 seconds). Continue directly from clip 1: use Extend if you can, otherwise use the last frame of clip 1 as the first frame.
Extend the previous clip by 10 seconds. Same man, same armchair, same voice.
0-2.5s SHOT 1 (B-roll): a friendly employee in an apron smiling at the camera in an aisle. His voice continues: "Thursday, introduce a team member."
2.5-5s SHOT 2 (B-roll): a paper grocery bag being packed with a bundle of produce and staples on a counter. His voice continues: "Friday, a weekend bundle."
5-7.5s SHOT 3 (A-roll, medium shot): back to the man, pointing over his shoulder as if at a map: "Saturday, your hours and location."
7.5-10s SHOT 4 (B-roll): hands slicing vegetables in a bright kitchen. His voice continues: "Sunday, one simple recipe."

STEP 3, CLIP 3 (10 seconds). Continue directly from clip 2 in the same way.
Extend the previous clip by 10 seconds. Same man, same armchair, same voice.
0-3s SHOT 1 (A-roll, medium shot): he sits back, relaxed: "This is a starter plan, not a rule."
3-5s SHOT 2 (B-roll): overhead shot of a blank weekly calendar on a desk and a hand placing seven sticky notes in a row. His voice continues: "Save this."
5-8s SHOT 3 (A-roll, medium shot): straight to camera: "DM the word GROW"
8-10s SHOT 4 (A-roll, close-up): "and Zenix will review your content." Hold still for the final second.

REPORT: For each clip, say which method you used (Extend or last-frame), and flag anything wrong with the face, hands, props, lip-sync, voice or text.
```

---

# Reel 4: PLAN

Studio: armchair. Paste the whole block below into the Agent prompt box.

```
TASK: Make the reel "PLAN". It is one 30-second vertical 9:16 video made of three consecutive 10-second Gemini Omni Flash 1.1 clips with native audio. Do all steps in order, then show me the three clips and your report.

PRESENTER: @presenter-armchair is the man. Keep his face, hair, beard, watch, outfit and studio identical in every clip.

STEP 0, FIRST FRAME: Generate the first-frame image using @presenter-armchair as the reference for the man and the studio. Image prompt: Edit the armchair reference to a wider framing showing the armchair, chalkboard and side table: he holds a smartphone at chest height in both hands, screen facing the lens, with a soft glowing orange circle on it and no text. No notebook. Deadpan look. Show it to me, check that the face matches the reference (regenerate once if it does not), then use it as the first frame of clip 1.

STEP 1, CLIP 1 (10 seconds, image-to-video from the first frame):
First frame: the uploaded image. The man sits in a green armchair in a wide shot in front of a chalkboard, holding a smartphone in both hands, a soft glowing orange circle on the screen.
0-3s SHOT 1 (A-roll, wide shot): he shakes his head slowly and says: "The Boost button doesn't make a post better."
3-4.3s SHOT 2 (A-roll, close-up on his thumb and the phone): he taps the glowing button and says: "Just louder."
4.3-6.5s SHOT 3 (B-roll): a generic social post on a phone with a pulsing red glow, text unreadable. His voice continues: "Before you press it:"
6.5-10s SHOT 4 (A-roll, medium close-up): back to him, direct: "what should a stranger do next? Visit, call, or message?"

STEP 2, CLIP 2 (10 seconds). Continue directly from clip 1: use Extend if you can, otherwise use the last frame of clip 1 as the first frame.
Extend the previous clip by 10 seconds. Same man, same armchair, same voice.
0-2s SHOT 1 (A-roll, medium shot): phone set aside, notebook and pen in his hands: "If you can't name it,"
2-5.8s SHOT 2 (B-roll): a generic vague social post on a phone held in front of a stream of anonymous people walking past. His voice continues: "you're paying to show a vague post to more strangers."
5.8-8.5s SHOT 3 (A-roll, close-up): he writes in the notebook and says: "Pick one offer, one audience, one action."
8.5-10s SHOT 4 (B-roll): overhead close-up of a pen writing three short lines in a notebook, text unreadable. No speech.

STEP 3, CLIP 3 (10 seconds). Continue directly from clip 2 in the same way.
Extend the previous clip by 10 seconds. Same man, same armchair, same voice.
0-2s SHOT 1 (B-roll): close-up of the pen circling the first line in the notebook. His voice continues: "Put the offer first."
2-6.5s SHOT 2 (A-roll, medium shot): back to the man, straight to camera: "DM the word PLAN and Zenix will review it before you spend."
6.5-10s SHOT 3 (A-roll, close-up): he smiles and taps his phone with his thumb: "Then boost it." Hold still for the final second.

REPORT: For each clip, say which method you used (Extend or last-frame), and flag anything wrong with the face, hands, props, lip-sync, voice or text.
```

---

# Reel 5: PREFLIGHT

Studio: office. Paste the whole block below into the Agent prompt box.

```
TASK: Make the reel "PREFLIGHT". It is one 30-second vertical 9:16 video made of three consecutive 10-second Gemini Omni Flash 1.1 clips with native audio. Do all steps in order, then show me the three clips and your report.

PRESENTER: @presenter-office is the man. Keep his face, hair, beard, watch, outfit and studio identical in every clip.

STEP 0, FIRST FRAME: Generate the first-frame image using @presenter-office as the reference for the man and the studio. Image prompt: Edit the office reference: he sits at the marble table holding a plain clipboard with a blank sheet showing four empty checkbox lines and no text, a pen in his right hand poised over the first line. He looks straight into the lens with a calm, serious expression. Show it to me, check that the face matches the reference (regenerate once if it does not), then use it as the first frame of clip 1.

STEP 1, CLIP 1 (10 seconds, image-to-video from the first frame):
First frame: the uploaded image. The man sits at a marble table in a modern office holding a clipboard, a pen poised over the first checkbox.
0-3s SHOT 1 (A-roll, medium shot): he clicks the pen, ticks the first box, and says: "Pilots run a checklist before takeoff."
3-5.6s SHOT 2 (A-roll, close-up): he points the pen at the camera: "Run one before you spend on ads."
5.6-8s SHOT 3 (B-roll): a phone showing generic notification icons for a call, a booking and a sale, text unreadable. His voice continues: "One: can you track a call,"
8-10s SHOT 4 (B-roll): a hand tapping a generic booking calendar on a tablet. His voice continues: "a booking, or a sale?"

STEP 2, CLIP 2 (10 seconds). Continue directly from clip 1: use Extend if you can, otherwise use the last frame of clip 1 as the first frame.
Extend the previous clip by 10 seconds. Same man, same office, same voice.
0-3.3s SHOT 1 (B-roll): a generic grocery ad on a phone with one clear product and a blurred price, slow push-in. His voice continues: "Two: does the ad promise one clear offer?"
3.3-6.6s SHOT 2 (A-roll, medium shot): back to the man, ticking the clipboard: "Three: does the landing page match that offer?"
6.6-10s SHOT 3 (B-roll): an overhead map with a circle drawn around a store pin, text unreadable. His voice continues: "Four: is your audience close enough to visit?"

STEP 3, CLIP 3 (10 seconds). Continue directly from clip 2 in the same way.
Extend the previous clip by 10 seconds. Same man, same office, same voice.
0-2.5s SHOT 1 (A-roll, close-up): he shakes his head once: "Any no? Fix it first."
2.5-4s SHOT 2 (B-roll): a hand sliding the clipboard across the marble table toward the camera. His voice continues: "Save this."
4-7s SHOT 3 (A-roll, medium shot): straight to camera: "DM the word PLAN"
7-10s SHOT 4 (A-roll, close-up): he ticks the last box and smiles: "and Zenix will review yours." Hold still for the final second.

REPORT: For each clip, say which method you used (Extend or last-frame), and flag anything wrong with the face, hands, props, lip-sync, voice or text.
```

---

# Reel 6: PAGE

Studio: office. Paste the whole block below into the Agent prompt box.

```
TASK: Make the reel "PAGE". It is one 30-second vertical 9:16 video made of three consecutive 10-second Gemini Omni Flash 1.1 clips with native audio. Do all steps in order, then show me the three clips and your report.

PRESENTER: @presenter-office is the man. Keep his face, hair, beard, watch, outfit and studio identical in every clip.

STEP 0, FIRST FRAME: Generate the first-frame image using @presenter-office as the reference for the man and the studio. Image prompt: Edit the office reference: the man sits upright at the marble table looking straight into the lens. His right hand rests on a plain, unbranded white milk carton standing on the table. The green folder sits closed to his left. Calm, composed, about to speak. Show it to me, check that the face matches the reference (regenerate once if it does not), then use it as the first frame of clip 1.

STEP 1, CLIP 1 (10 seconds, image-to-video from the first frame):
First frame: the uploaded image. The man sits upright at a marble table in a modern office, his right hand resting on a plain white milk carton.
0-3.3s SHOT 1 (A-roll, medium shot): he lifts the carton on "milk" and lowers it out of frame below the table on "basement": "You wouldn't hide the milk in the basement."
3.3-5.2s SHOT 2 (A-roll, tight close-up): straight into the lens with one raised eyebrow: "Your landing page does."
5.2-7.6s SHOT 3 (B-roll): a laptop showing a deliberately cluttered generic landing page, blurred, slow push-in. His voice continues: "Someone clicked your ad for one offer,"
7.6-10s SHOT 4 (A-roll, medium shot, slight angle): dry and direct: "and now they're hunting through banners."

STEP 2, CLIP 2 (10 seconds). Continue directly from clip 1: use Extend if you can, otherwise use the last frame of clip 1 as the first frame.
Extend the previous clip by 10 seconds. Same man, same office, same voice.
0-3s SHOT 1 (A-roll, close-up): a small shrug: "If the deal isn't obvious, they leave."
3-6.5s SHOT 2 (B-roll): a clean landing page mockup on a laptop with one big offer block at the top, all text unreadable, slow push-in. His voice continues: "Put your ad's exact offer at the top,"
6.5-10s SHOT 3 (A-roll, medium shot): he counts on his fingers: "with the price and one reason to trust you."

STEP 3, CLIP 3 (10 seconds). Continue directly from clip 2 in the same way.
Extend the previous clip by 10 seconds. Same man, same office, same voice.
0-3s SHOT 1 (B-roll): a finger tapping a large green button on a clean generic page on a phone. His voice continues: "Then give them one clear button."
3-7s SHOT 2 (A-roll, medium shot): back to the man, straight to camera: "DM the word PAGE and Zenix will check your ad and page together."
7-10s SHOT 3 (A-roll, close-up): he smiles slightly, holding still for the final second.

REPORT: For each clip, say which method you used (Extend or last-frame), and flag anything wrong with the face, hands, props, lip-sync, voice or text.
```

---

# Reel 7: HOOKS

Studio: couch. Paste the whole block below into the Agent prompt box.

```
TASK: Make the reel "HOOKS". It is one 30-second vertical 9:16 video made of three consecutive 10-second Gemini Omni Flash 1.1 clips with native audio. Do all steps in order, then show me the three clips and your report.

PRESENTER: @presenter-couch is the man. Keep his face, hair, beard, watch, outfit and studio identical in every clip.

STEP 0, FIRST FRAME: Generate the first-frame image using @presenter-couch as the reference for the man and the studio. Image prompt: Edit the couch reference: he holds a smartphone up at arm's length with the lens facing us, as if filming the viewer, his face partly visible beside it, deadpan. The microphone stays in frame. Show it to me, check that the face matches the reference (regenerate once if it does not), then use it as the first frame of clip 1.

STEP 1, CLIP 1 (10 seconds, image-to-video from the first frame):
First frame: the uploaded image. The man sits on a couch in a warm wood-slat podcast studio, holding a smartphone up as if filming.
0-3.5s SHOT 1 (A-roll, medium shot): he lowers the phone and looks into the lens: "Your supermarket does not need a video team."
3.5-5.5s SHOT 2 (A-roll, close-up): he holds up three fingers: "Film these three reels."
5.5-8.5s SHOT 3 (B-roll): a hand picking the best-looking mango from a shelf and turning it in the light. His voice continues: "One: pick the best item on the shelf,"
8.5-10s SHOT 4 (A-roll, medium shot): back to him, one nod: "and say why."

STEP 2, CLIP 2 (10 seconds). Continue directly from clip 1: use Extend if you can, otherwise use the last frame of clip 1 as the first frame.
Extend the previous clip by 10 seconds. Same man, same couch, same voice.
0-4s SHOT 1 (B-roll): a phone filming a well-lit deal display with a blank price tag and a blurred aisle sign. His voice continues: "Two: show one deal with the price and the aisle."
4-8s SHOT 2 (A-roll, medium shot): back to the man, counting on his fingers: "Three: answer a customer question standing in the store."
8-10s SHOT 3 (B-roll): a store employee answering a shopper's question in an aisle, soft focus, no speech.

STEP 3, CLIP 3 (10 seconds). Continue directly from clip 2 in the same way.
Extend the previous clip by 10 seconds. Same man, same couch, same voice.
0-2.5s SHOT 1 (A-roll, close-up): "Keep each under thirty seconds."
2.5-4.3s SHOT 2 (B-roll): a phone recording with a generic timer icon in the corner. His voice continues: "Save this list."
4.3-7.3s SHOT 3 (A-roll, medium shot): straight to camera: "DM the word STORE"
7.3-10s SHOT 4 (A-roll, close-up): "and Zenix will review your supermarket marketing." Hold still for the final second.

REPORT: For each clip, say which method you used (Extend or last-frame), and flag anything wrong with the face, hands, props, lip-sync, voice or text.
```

---

# Reel 8: REPLY

Studio: office. Paste the whole block below into the Agent prompt box.

```
TASK: Make the reel "REPLY". It is one 30-second vertical 9:16 video made of three consecutive 10-second Gemini Omni Flash 1.1 clips with native audio. Do all steps in order, then show me the three clips and your report.

PRESENTER: @presenter-office is the man. Keep his face, hair, beard, watch, outfit and studio identical in every clip.

STEP 0, FIRST FRAME: Generate the first-frame image using @presenter-office as the reference for the man and the studio. Image prompt: Edit the office reference: he sits at the marble table, his right hand hovering over a plain silver desk service bell on the table, looking into the lens with a patient, slightly bored expression. No folder. Show it to me, check that the face matches the reference (regenerate once if it does not), then use it as the first frame of clip 1.

STEP 1, CLIP 1 (10 seconds, image-to-video from the first frame):
First frame: the uploaded image. The man sits at a marble table in a modern office, his hand hovering over a silver desk service bell.
0-4s SHOT 1 (A-roll, medium shot): he taps the bell on "register" and again on "nobody", looks into the lens, and says: "Your DMs are a cash register nobody is standing at."
4-6.8s SHOT 2 (B-roll): a phone with stacking notification badges, all text blurred and unreadable. His voice continues: "A shopper asks your hours, and waits."
6.8-10s SHOT 3 (A-roll, close-up): he holds up three fingers: "Set one automatic reply that does three things."

STEP 2, CLIP 2 (10 seconds). Continue directly from clip 1: use Extend if you can, otherwise use the last frame of clip 1 as the first frame.
Extend the previous clip by 10 seconds. Same man, same office, same voice.
0-1.5s SHOT 1 (A-roll, close-up): "Say thanks."
1.5-5.3s SHOT 2 (B-roll): a phone showing a simple generic chat with one reply bubble, text unreadable. His voice continues: "Answer the top three questions: hours, location, and offers."
5.3-7.3s SHOT 3 (A-roll, medium shot): back to the man, open hand: "Offer a human for everything else."
7.3-10s SHOT 4 (B-roll): a hand testing a chat reply on a second phone. His voice continues: "Test it from a customer's phone."

STEP 3, CLIP 3 (10 seconds). Continue directly from clip 2 in the same way.
Extend the previous clip by 10 seconds. Same man, same office, same voice.
0-4s SHOT 1 (A-roll, close-up): "Automation handles the routine. People handle the rest."
4-5.3s SHOT 2 (B-roll): a hand sliding a blank template card across the marble table. His voice continues: "Save this template."
5.3-8.3s SHOT 3 (A-roll, medium shot): straight to camera: "DM the word REPLY"
8.3-10s SHOT 4 (A-roll, close-up): "and Zenix will review your setup." He taps the bell once and smiles. Hold still for the final second.

REPORT: For each clip, say which method you used (Extend or last-frame), and flag anything wrong with the face, hands, props, lip-sync, voice or text.
```

---

# Reel 9: SQUINT

Studio: couch. Paste the whole block below into the Agent prompt box.

```
TASK: Make the reel "SQUINT". It is one 30-second vertical 9:16 video made of three consecutive 10-second Gemini Omni Flash 1.1 clips with native audio. Do all steps in order, then show me the three clips and your report.

PRESENTER: @presenter-couch is the man. Keep his face, hair, beard, watch, outfit and studio identical in every clip.

STEP 0, FIRST FRAME: Generate the first-frame image using @presenter-couch as the reference for the man and the studio. Image prompt: Edit the couch reference: he holds a large generic supermarket weekly flyer beside his face in his right hand, crowded with small red price bursts and produce photos, all text blurred and unreadable, squinting at it with one eye narrowed. The microphone stays in frame. Show it to me, check that the face matches the reference (regenerate once if it does not), then use it as the first frame of clip 1.

STEP 1, CLIP 1 (10 seconds, image-to-video from the first frame):
First frame: the uploaded image. The man sits on a couch in a warm wood-slat podcast studio, holding a busy supermarket flyer beside his face, squinting at it.
0-3s SHOT 1 (A-roll, medium shot): he squints hard at the flyer, slowly lowers it, and says: "Squint at your weekly poster."
3-6.3s SHOT 2 (A-roll, close-up, raised eyebrow): "If the deal disappears, shoppers might miss it too."
6.3-8.3s SHOT 3 (B-roll): a busy generic flyer in soft focus where nothing stands out. His voice continues: "This is the squint test."
8.3-10s SHOT 4 (A-roll, medium shot): "It takes five seconds."

STEP 2, CLIP 2 (10 seconds). Continue directly from clip 1: use Extend if you can, otherwise use the last frame of clip 1 as the first frame.
Extend the previous clip by 10 seconds. Same man, same couch, same voice.
0-3s SHOT 1 (A-roll, medium shot): he narrows his eyes slightly at the camera: "Blur your eyes and look for three things."
3-6.5s SHOT 2 (B-roll): the same flyer heavily blurred, with three soft glowing areas where a hero deal, a price and a store name would sit. His voice continues: "The hero deal, the price, and the store name."
6.5-10s SHOT 3 (A-roll, close-up): he shrugs: "If any one vanishes, it is too small."

STEP 3, CLIP 3 (10 seconds). Continue directly from clip 2 in the same way.
Extend the previous clip by 10 seconds. Same man, same couch, same voice.
0-3.8s SHOT 1 (A-roll, medium shot): he holds up a phone: "Make that one bigger, then test it on your phone."
3.8-6s SHOT 2 (B-roll): a hand holding a phone showing a blurred clean poster with one big deal. His voice continues: "Save this for your next poster."
6-10s SHOT 3 (A-roll, close-up): straight to camera: "DM the word POSTER and Zenix will review yours." Hold still for the final second.

REPORT: For each clip, say which method you used (Extend or last-frame), and flag anything wrong with the face, hands, props, lip-sync, voice or text.
```

---

# Reel 10: GROW

Studio: couch. Paste the whole block below into the Agent prompt box.

```
TASK: Make the reel "GROW". It is one 30-second vertical 9:16 video made of three consecutive 10-second Gemini Omni Flash 1.1 clips with native audio. Do all steps in order, then show me the three clips and your report.

PRESENTER: @presenter-couch is the man. Keep his face, hair, beard, watch, outfit and studio identical in every clip.

STEP 0, FIRST FRAME: I have attached my finished first-frame image as @grow-megaphone-frame (man on the couch holding a small toy megaphone near his chin). Use it exactly as the first frame of clip 1. Do not regenerate it.

STEP 1, CLIP 1 (10 seconds, image-to-video from the first frame):
First frame: the uploaded image. The man sits on a couch in a warm wood-slat podcast studio with a microphone in frame, holding a small toy megaphone near his chin.
0-2.5s SHOT 1 (A-roll, medium shot, slow push-in): he brings the megaphone the last few inches toward his mouth, stops, says nothing, lowers it and sets it on the couch beside him. No sound comes from the megaphone.
2.5-4s SHOT 2 (A-roll, medium shot): straight to camera, deadpan: "Nobody follows a megaphone."
4-6.8s SHOT 3 (A-roll, close-up): "If your supermarket's page only shouts buy now,"
6.8-8.3s SHOT 4 (B-roll): a phone scrolling a feed of near-identical loud red grocery sale posts, text blurred. His voice continues: "why would anyone stay?"
8.3-10s SHOT 5 (A-roll, medium shot): he lifts three fanned cards beside his face: "Three posts, same pitch,"

STEP 2, CLIP 2 (10 seconds). Continue directly from clip 1: use Extend if you can, otherwise use the last frame of clip 1 as the first frame.
Extend the previous clip by 10 seconds. Same man, same couch, same voice.
0-3.3s SHOT 1 (A-roll, close-up): holding the fanned cards, he slowly shakes his head: "nothing to answer, nothing to save, nothing to share."
3.3-6.6s SHOT 2 (A-roll, medium shot): cards lowered, he leans in with an open palm: "Answer one real customer question in every sales post."
6.6-10s SHOT 3 (B-roll): two quick inserts: hands preparing fresh vegetables on a wooden board, then hands setting out a product display. His voice continues: "Show how a product is used,"

STEP 3, CLIP 3 (10 seconds). Continue directly from clip 2 in the same way.
Extend the previous clip by 10 seconds. Same man, same couch, same voice.
0-2.2s SHOT 1 (B-roll): a friendly store employee talking to camera in a produce aisle, soft focus. His voice continues: "or let your team speak."
2.2-5s SHOT 2 (A-roll, medium shot): back to the man: "Then connect that post to a sale."
5-7.5s SHOT 3 (A-roll, medium shot): straight to camera: "DM the word GROW"
7.5-10s SHOT 4 (A-roll, close-up): "and Zenix will review your content." He smiles slightly. Hold still for the final second.

REPORT: For each clip, say which method you used (Extend or last-frame), and flag anything wrong with the face, hands, props, lip-sync, voice or text.
```

---

## After the Agent finishes

1. Check hands, props, face and lip-sync on every clip before you approve any extend or re-run.
2. If the voice changed between clips, record or generate one clean voiceover of the reel's script and replace the audio in the edit.
3. Add captions, list cards, the 400% graphic and any other readable text in the editor. Never rely on generated text.
4. Turn on Instagram's AI disclosure when posting. The CEO and owner approve before anything is published.
