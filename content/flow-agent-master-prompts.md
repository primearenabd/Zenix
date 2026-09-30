# Zenix Reels: Flow Prompts (Agent for clip 1, Extend for clips 2 and 3)

Status: draft. Nothing is generated or published. Revised after the first Agent test failed on clip 2.

---

## Why clip 2 failed, and the fix

**What you saw:** the Agent wrote "use the last frame of the previous clip as a reference" into the prompt and attached an "Ingredient image" that shows as a broken image (only its label appears). Clip 2 then failed with "Something went wrong", and the detailed report had no image.

**What I found (facts from public sources):**
- "Something went wrong" is a generic Flow error. It covers server overload, credit problems, content checks on the finished video, and media problems such as a missing, oversized or unusual-format image. Flow accepts at most three ingredient images in one prompt. Sources: [Flow troubleshooting guide](https://apipass.dev/blogs/google-flow-errors-troubleshooting-guide), [Flow generation failed fix](https://whiskailabs.net/google-flow-generation-failed-fix/).
- Flow has its own **Extend clip** option on a finished clip. Omni 1.1 reads up to 10 seconds of the previous clip. An extension uses only what it sees in that video, not your earlier prompt, so every extension prompt must repeat the full description of the man and the studio. Opening the prompt with "The scene continues without a cut." is the clearest signal for a seamless join. Sources: [Omni 1.1 extension guide](https://www.atlascloud.ai/blog/tips/gemini-omni-flash-1.1-video-extension), [Extending a video (Omni Flash 1.1)](https://runware.ai/docs/models/google-gemini-omni-flash-1-1/guides/extending-video), [Flow Omni tutorial](https://www.mindstudio.ai/blog/how-to-use-google-flow-gemini-omni-video-editing).

**What I infer (not confirmed by Google):** the Agent cannot pull a frame out of a finished clip by itself. It describes the step but attaches nothing, so the next generation fails. The failed screenshot fits this: a broken ingredient image plus instruction text pasted into the video prompt.

**Also noticed:** the Agent's own prompt contained "Voice: Charon, calm, informative, male, deadpan". That suggests Omni takes a named voice. Using the same named voice in every clip should reduce voice drift. Check that Charon is available in your voice options.

**The fix: stop asking the Agent to chain clips.**
1. **Agent:** use it only for what it does well: the first-frame image and clip 1 (and batches of clip 1s for several reels at once).
2. **Manual Extend:** on the finished clip, click **Extend clip** and paste the clip 2 prompt below. Then extend the result with the clip 3 prompt. That is two extra clicks per reel.
3. **Fallback if Extend is missing or fails:** scrub to the last frame of the clip, save it as a screenshot (1080x1920 JPEG or PNG, under 5 MB), upload it as an ingredient, and run image-to-video with the clip 2 prompt. Do not use HEIC files.
4. **If a clip fails:** check your credits, hard refresh in Chrome, and look in the Library in case the clip actually rendered.

---

## Set up once

**1. Upload reference images** and tag each in Flow:
- `@presenter-armchair`, `@presenter-office`, `@presenter-couch` (the three studio images)
- `@map-frame` (your finished MAP first frame) and `@grow-megaphone-frame` (your finished GROW megaphone frame)

Keep each prompt to no more than three ingredient images.

**2. Agent project instructions** (paste once; turn Agent on):

```
ROLE: You are the video producer for Zenix, a marketing agency that specialises in supermarkets and grocery stores.
GOAL: Produce the first 10-second clip of vertical 9:16 Instagram reels using Gemini Omni Flash 1.1 with native audio.
CONSISTENCY: The presenter is always the man in the tagged presenter reference. Keep his face, hair, beard, watch, outfit and studio identical. Tell me if an asset looks off.
VOICE: Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
LOOK: Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. Every shot lasts 2 to 4 seconds.
TEXT: Never render readable text, logos, subtitles or watermarks, except what is already inside a first-frame image I supply.
PROPS AND B-ROLL: Plain, unbranded props. B-roll is generic and never presented as a real named store.
WORKFLOW: Generate only the clip I ask for. Do not try to chain, extend or extract frames. I will extend clips myself. Finish with a short report on anything wrong with the face, hands, props, lip-sync, voice or text. Do not publish anything.
```

**3. Order:** MAP, STORE, WEEK, PLAN, PREFLIGHT, PAGE, HOOKS, REPLY, SQUINT, GROW. Test MAP fully before doing more, and check your credit balance first.

---

# Reel 1: MAP

Studio: armchair.

**Step A: paste in the Agent prompt box (clip 1)**

```
TASK: Make clip 1 of the reel "MAP": one 10-second vertical 9:16 Gemini Omni Flash 1.1 clip with native audio.

PRESENTER: @presenter-armchair is the man. Keep his face, hair, beard, watch, outfit and studio identical.

FIRST FRAME: Use my attached first-frame image @map-frame exactly as the first frame of the clip. Do not regenerate it.

CLIP 1 (10 seconds, image-to-video from the first frame):
First frame: the uploaded image. The man sits in a green armchair in front of a chalkboard in a warm study, holding a smartphone at chest height showing a map listing with a red CLOSED label, his other index finger pointing at the screen. Keep the phone screen exactly as in the image and hold the phone still.
0-1.8s SHOT 1 (A-roll, medium shot): deadpan, looking into the lens, he says: "Your store sign says open."
1.8-3.2s SHOT 2 (A-roll, tight close-up on the phone and his pointing finger): he taps the screen twice with his index finger and says: "Google says closed."
3.2-5s SHOT 3 (A-roll, medium shot, slight low angle): he lifts his eyebrows and tilts his head at the phone: "Guess who shoppers believe."
5-7.5s SHOT 4 (B-roll): a shopper glances at a phone outside a storefront, frowns. His voice continues: "Some won't call to check."
7.5-10s SHOT 5 (B-roll): the same shopper turns and walks away down the street at dusk. His voice continues: "They'll just go elsewhere."

Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.

Generate only this clip. Do not chain or extend. Report anything wrong with the face, hands, props, lip-sync, voice or text.
```

**Step B: on the finished clip 1, click Extend clip and paste (clip 2)**

```
The scene continues without a cut. The same man: short black hair, trimmed beard and moustache, cream knit sweater, black watch on his left wrist, sitting in a green velvet armchair in front of a dark green chalkboard with chalk diagrams, a warm bulb lamp on the right.
0-4s SHOT 1 (B-roll): a car driving past a warm-lit storefront at dusk, slow tracking shot. His voice continues: "Nearby shoppers can be gone before they ever reach your door."
4-6.5s SHOT 2 (A-roll, medium shot): back to the man, phone lowered, a pen in his hand: "Check today's hours,"
6.5-10s SHOT 3 (B-roll): close-up of a hand ticking items on a blank list beside a generic shop door hours sign, text unreadable. His voice continues: "then weekends and holidays."
Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.
```

**Step C: on the finished clip 2, click Extend clip and paste (clip 3)**

```
The scene continues without a cut. The same man: short black hair, trimmed beard and moustache, cream knit sweater, black watch on his left wrist, sitting in a green velvet armchair in front of a dark green chalkboard with chalk diagrams, a warm bulb lamp on the right.
0-4s SHOT 1 (B-roll): a hand holding a phone over a generic business listing, tapping the call, directions and photos icons in turn, all text unreadable. His voice continues: "Test your phone number, directions, and photos on a customer's phone."
4-7s SHOT 2 (A-roll, medium shot): back to the man, straight to camera: "DM the word MAP"
7-10s SHOT 3 (A-roll, close-up): he smiles slightly: "and Zenix will review your local listing." Hold still for the final second.
Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.
```

---

# Reel 2: STORE

Studio: office.

**Step A: paste in the Agent prompt box (clip 1)**

```
TASK: Make clip 1 of the reel "STORE": one 10-second vertical 9:16 Gemini Omni Flash 1.1 clip with native audio.

PRESENTER: @presenter-office is the man. Keep his face, hair, beard, watch, outfit and studio identical.

FIRST FRAME: First generate the first-frame image using @presenter-office as the reference for the man and the studio. Image prompt: Edit the office reference: he sits slightly right of centre with one hand flat on the marble table and the other on the open green folder, which holds one blank white sheet. He leans in slightly and looks straight into the lens, serious and focused. Clean, empty wall to his left. Show it to me and check the face matches the reference (regenerate once if not). Then use it as the first frame of the clip.

CLIP 1 (10 seconds, image-to-video from the first frame):
First frame: the uploaded image. The man sits slightly right of centre at a marble table in a modern office, one hand flat on the table, the other on an open green folder, clean empty wall to his left.
0-2.6s SHOT 1 (A-roll, medium shot): he leans in, looks into the lens, and says: "Four hundred percent. That's not a typo." He taps the table once on "typo" and points to the side.
2.6-5.4s SHOT 2 (A-roll, slow push-in, medium close-up): serious and steady: "Khaamar Baari Supermarket achieved four hundred percent revenue growth"
5.4-8.2s SHOT 3 (A-roll, close-up from a slightly different angle): "in one year while working with Zenix."
8.2-10s SHOT 4 (A-roll, medium shot): he sits back slightly and gives one small nod. No speech.

Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.

Generate only this clip. Do not chain or extend. Report anything wrong with the face, hands, props, lip-sync, voice or text.
```

**Step B: on the finished clip 1, click Extend clip and paste (clip 2)**

```
The scene continues without a cut. The same man: short black hair, trimmed beard and moustache, navy blazer over a white open-collar shirt, black watch, sitting at a marble table in a modern office with a warm lamp on the left.
0-3.5s SHOT 1 (A-roll, medium shot): calm and direct: "Specific proof builds trust, and a specific offer does too."
3.5-6.5s SHOT 2 (B-roll): a generic fresh produce display with one clearly highlighted item and a blank price card, slow drift. His voice continues: "Lead with your strongest deal."
6.5-10s SHOT 3 (B-roll): a phone recording a short vertical video of a produce display with a map pin icon in the corner. His voice continues: "Show the price and where to find the store,"
Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.
```

**Step C: on the finished clip 2, click Extend clip and paste (clip 3)**

```
The scene continues without a cut. The same man: short black hair, trimmed beard and moustache, navy blazer over a white open-collar shirt, black watch, sitting at a marble table in a modern office with a warm lamp on the left.
0-1.5s SHOT 1 (B-roll): the phone video continues, close-up. His voice continues: "in one short video."
1.5-4.5s SHOT 2 (B-roll): a phone showing a generic business listing with a map pin and opening hours, text unreadable. His voice continues: "Then make sure your Google listing matches."
4.5-7.5s SHOT 3 (A-roll, medium shot): back to the man, hands clasped, straight to camera: "DM the word STORE"
7.5-10s SHOT 4 (A-roll, close-up): calm and inviting: "and Zenix will review your supermarket marketing." Hold still for the final second.
Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.
```

---

# Reel 3: WEEK

Studio: armchair.

**Step A: paste in the Agent prompt box (clip 1)**

```
TASK: Make clip 1 of the reel "WEEK": one 10-second vertical 9:16 Gemini Omni Flash 1.1 clip with native audio.

PRESENTER: @presenter-armchair is the man. Keep his face, hair, beard, watch, outfit and studio identical.

FIRST FRAME: First generate the first-frame image using @presenter-armchair as the reference for the man and the studio. Image prompt: Edit the armchair reference: he sits in the armchair turned slightly toward the chalkboard behind him, a pen in his right hand pointing at the board, looking straight into the lens with a confident, slightly amused expression. No notebook. Show it to me and check the face matches the reference (regenerate once if not). Then use it as the first frame of the clip.

CLIP 1 (10 seconds, image-to-video from the first frame):
First frame: the uploaded image. The man sits in a green armchair in front of a chalkboard, a pen in his hand pointed at the board.
0-3.3s SHOT 1 (A-roll, medium shot): he taps the chalkboard seven times with the pen and says, looking into the lens: "Steal this seven-day content plan for your supermarket."
3.3-5.3s SHOT 2 (B-roll): a hand unpacking fresh produce crates in a bright back room. His voice continues: "Monday, show what just arrived."
5.3-7.3s SHOT 3 (A-roll, close-up): he holds up one finger: "Tuesday, your hero deal."
7.3-10s SHOT 4 (B-roll): a store employee answering a question for a shopper in an aisle, soft focus. His voice continues: "Wednesday, answer a customer question."

Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.

Generate only this clip. Do not chain or extend. Report anything wrong with the face, hands, props, lip-sync, voice or text.
```

**Step B: on the finished clip 1, click Extend clip and paste (clip 2)**

```
The scene continues without a cut. The same man: short black hair, trimmed beard and moustache, cream knit sweater, black watch on his left wrist, sitting in a green velvet armchair in front of a dark green chalkboard with chalk diagrams, a warm bulb lamp on the right.
0-2.5s SHOT 1 (B-roll): a friendly employee in an apron smiling at the camera in an aisle. His voice continues: "Thursday, introduce a team member."
2.5-5s SHOT 2 (B-roll): a paper grocery bag being packed with a bundle of produce and staples on a counter. His voice continues: "Friday, a weekend bundle."
5-7.5s SHOT 3 (A-roll, medium shot): back to the man, pointing over his shoulder as if at a map: "Saturday, your hours and location."
7.5-10s SHOT 4 (B-roll): hands slicing vegetables in a bright kitchen. His voice continues: "Sunday, one simple recipe."
Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.
```

**Step C: on the finished clip 2, click Extend clip and paste (clip 3)**

```
The scene continues without a cut. The same man: short black hair, trimmed beard and moustache, cream knit sweater, black watch on his left wrist, sitting in a green velvet armchair in front of a dark green chalkboard with chalk diagrams, a warm bulb lamp on the right.
0-3s SHOT 1 (A-roll, medium shot): he sits back, relaxed: "This is a starter plan, not a rule."
3-5s SHOT 2 (B-roll): overhead shot of a blank weekly calendar on a desk and a hand placing seven sticky notes in a row. His voice continues: "Save this."
5-8s SHOT 3 (A-roll, medium shot): straight to camera: "DM the word GROW"
8-10s SHOT 4 (A-roll, close-up): "and Zenix will review your content." Hold still for the final second.
Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.
```

---

# Reel 4: PLAN

Studio: armchair.

**Step A: paste in the Agent prompt box (clip 1)**

```
TASK: Make clip 1 of the reel "PLAN": one 10-second vertical 9:16 Gemini Omni Flash 1.1 clip with native audio.

PRESENTER: @presenter-armchair is the man. Keep his face, hair, beard, watch, outfit and studio identical.

FIRST FRAME: First generate the first-frame image using @presenter-armchair as the reference for the man and the studio. Image prompt: Edit the armchair reference to a wider framing showing the armchair, chalkboard and side table: he holds a smartphone at chest height in both hands, screen facing the lens, with a soft glowing orange circle on it and no text. No notebook. Deadpan look. Show it to me and check the face matches the reference (regenerate once if not). Then use it as the first frame of the clip.

CLIP 1 (10 seconds, image-to-video from the first frame):
First frame: the uploaded image. The man sits in a green armchair in a wide shot in front of a chalkboard, holding a smartphone in both hands, a soft glowing orange circle on the screen.
0-3s SHOT 1 (A-roll, wide shot): he shakes his head slowly and says: "The Boost button doesn't make a post better."
3-4.3s SHOT 2 (A-roll, close-up on his thumb and the phone): he taps the glowing button and says: "Just louder."
4.3-6.5s SHOT 3 (B-roll): a generic social post on a phone with a pulsing red glow, text unreadable. His voice continues: "Before you press it:"
6.5-10s SHOT 4 (A-roll, medium close-up): back to him, direct: "what should a stranger do next? Visit, call, or message?"

Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.

Generate only this clip. Do not chain or extend. Report anything wrong with the face, hands, props, lip-sync, voice or text.
```

**Step B: on the finished clip 1, click Extend clip and paste (clip 2)**

```
The scene continues without a cut. The same man: short black hair, trimmed beard and moustache, cream knit sweater, black watch on his left wrist, sitting in a green velvet armchair in front of a dark green chalkboard with chalk diagrams, a warm bulb lamp on the right.
0-2s SHOT 1 (A-roll, medium shot): phone set aside, notebook and pen in his hands: "If you can't name it,"
2-5.8s SHOT 2 (B-roll): a generic vague social post on a phone held in front of a stream of anonymous people walking past. His voice continues: "you're paying to show a vague post to more strangers."
5.8-8.5s SHOT 3 (A-roll, close-up): he writes in the notebook and says: "Pick one offer, one audience, one action."
8.5-10s SHOT 4 (B-roll): overhead close-up of a pen writing three short lines in a notebook, text unreadable. No speech.
Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.
```

**Step C: on the finished clip 2, click Extend clip and paste (clip 3)**

```
The scene continues without a cut. The same man: short black hair, trimmed beard and moustache, cream knit sweater, black watch on his left wrist, sitting in a green velvet armchair in front of a dark green chalkboard with chalk diagrams, a warm bulb lamp on the right.
0-2s SHOT 1 (B-roll): close-up of the pen circling the first line in the notebook. His voice continues: "Put the offer first."
2-6.5s SHOT 2 (A-roll, medium shot): back to the man, straight to camera: "DM the word PLAN and Zenix will review it before you spend."
6.5-10s SHOT 3 (A-roll, close-up): he smiles and taps his phone with his thumb: "Then boost it." Hold still for the final second.
Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.
```

---

# Reel 5: PREFLIGHT

Studio: office.

**Step A: paste in the Agent prompt box (clip 1)**

```
TASK: Make clip 1 of the reel "PREFLIGHT": one 10-second vertical 9:16 Gemini Omni Flash 1.1 clip with native audio.

PRESENTER: @presenter-office is the man. Keep his face, hair, beard, watch, outfit and studio identical.

FIRST FRAME: First generate the first-frame image using @presenter-office as the reference for the man and the studio. Image prompt: Edit the office reference: he sits at the marble table holding a plain clipboard with a blank sheet showing four empty checkbox lines and no text, a pen in his right hand poised over the first line. He looks straight into the lens with a calm, serious expression. Show it to me and check the face matches the reference (regenerate once if not). Then use it as the first frame of the clip.

CLIP 1 (10 seconds, image-to-video from the first frame):
First frame: the uploaded image. The man sits at a marble table in a modern office holding a clipboard, a pen poised over the first checkbox.
0-3s SHOT 1 (A-roll, medium shot): he clicks the pen, ticks the first box, and says: "Pilots run a checklist before takeoff."
3-5.6s SHOT 2 (A-roll, close-up): he points the pen at the camera: "Run one before you spend on ads."
5.6-8s SHOT 3 (B-roll): a phone showing generic notification icons for a call, a booking and a sale, text unreadable. His voice continues: "One: can you track a call,"
8-10s SHOT 4 (B-roll): a hand tapping a generic booking calendar on a tablet. His voice continues: "a booking, or a sale?"

Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.

Generate only this clip. Do not chain or extend. Report anything wrong with the face, hands, props, lip-sync, voice or text.
```

**Step B: on the finished clip 1, click Extend clip and paste (clip 2)**

```
The scene continues without a cut. The same man: short black hair, trimmed beard and moustache, navy blazer over a white open-collar shirt, black watch, sitting at a marble table in a modern office with a warm lamp on the left.
0-3.3s SHOT 1 (B-roll): a generic grocery ad on a phone with one clear product and a blurred price, slow push-in. His voice continues: "Two: does the ad promise one clear offer?"
3.3-6.6s SHOT 2 (A-roll, medium shot): back to the man, ticking the clipboard: "Three: does the landing page match that offer?"
6.6-10s SHOT 3 (B-roll): an overhead map with a circle drawn around a store pin, text unreadable. His voice continues: "Four: is your audience close enough to visit?"
Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.
```

**Step C: on the finished clip 2, click Extend clip and paste (clip 3)**

```
The scene continues without a cut. The same man: short black hair, trimmed beard and moustache, navy blazer over a white open-collar shirt, black watch, sitting at a marble table in a modern office with a warm lamp on the left.
0-2.5s SHOT 1 (A-roll, close-up): he shakes his head once: "Any no? Fix it first."
2.5-4s SHOT 2 (B-roll): a hand sliding the clipboard across the marble table toward the camera. His voice continues: "Save this."
4-7s SHOT 3 (A-roll, medium shot): straight to camera: "DM the word PLAN"
7-10s SHOT 4 (A-roll, close-up): he ticks the last box and smiles: "and Zenix will review yours." Hold still for the final second.
Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.
```

---

# Reel 6: PAGE

Studio: office.

**Step A: paste in the Agent prompt box (clip 1)**

```
TASK: Make clip 1 of the reel "PAGE": one 10-second vertical 9:16 Gemini Omni Flash 1.1 clip with native audio.

PRESENTER: @presenter-office is the man. Keep his face, hair, beard, watch, outfit and studio identical.

FIRST FRAME: First generate the first-frame image using @presenter-office as the reference for the man and the studio. Image prompt: Edit the office reference: the man sits upright at the marble table looking straight into the lens. His right hand rests on a plain, unbranded white milk carton standing on the table. The green folder sits closed to his left. Calm, composed, about to speak. Show it to me and check the face matches the reference (regenerate once if not). Then use it as the first frame of the clip.

CLIP 1 (10 seconds, image-to-video from the first frame):
First frame: the uploaded image. The man sits upright at a marble table in a modern office, his right hand resting on a plain white milk carton.
0-3.3s SHOT 1 (A-roll, medium shot): he lifts the carton on "milk" and lowers it out of frame below the table on "basement": "You wouldn't hide the milk in the basement."
3.3-5.2s SHOT 2 (A-roll, tight close-up): straight into the lens with one raised eyebrow: "Your landing page does."
5.2-7.6s SHOT 3 (B-roll): a laptop showing a deliberately cluttered generic landing page, blurred, slow push-in. His voice continues: "Someone clicked your ad for one offer,"
7.6-10s SHOT 4 (A-roll, medium shot, slight angle): dry and direct: "and now they're hunting through banners."

Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.

Generate only this clip. Do not chain or extend. Report anything wrong with the face, hands, props, lip-sync, voice or text.
```

**Step B: on the finished clip 1, click Extend clip and paste (clip 2)**

```
The scene continues without a cut. The same man: short black hair, trimmed beard and moustache, navy blazer over a white open-collar shirt, black watch, sitting at a marble table in a modern office with a warm lamp on the left.
0-3s SHOT 1 (A-roll, close-up): a small shrug: "If the deal isn't obvious, they leave."
3-6.5s SHOT 2 (B-roll): a clean landing page mockup on a laptop with one big offer block at the top, all text unreadable, slow push-in. His voice continues: "Put your ad's exact offer at the top,"
6.5-10s SHOT 3 (A-roll, medium shot): he counts on his fingers: "with the price and one reason to trust you."
Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.
```

**Step C: on the finished clip 2, click Extend clip and paste (clip 3)**

```
The scene continues without a cut. The same man: short black hair, trimmed beard and moustache, navy blazer over a white open-collar shirt, black watch, sitting at a marble table in a modern office with a warm lamp on the left.
0-3s SHOT 1 (B-roll): a finger tapping a large green button on a clean generic page on a phone. His voice continues: "Then give them one clear button."
3-7s SHOT 2 (A-roll, medium shot): back to the man, straight to camera: "DM the word PAGE and Zenix will check your ad and page together."
7-10s SHOT 3 (A-roll, close-up): he smiles slightly, holding still for the final second.
Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.
```

---

# Reel 7: HOOKS

Studio: couch.

**Step A: paste in the Agent prompt box (clip 1)**

```
TASK: Make clip 1 of the reel "HOOKS": one 10-second vertical 9:16 Gemini Omni Flash 1.1 clip with native audio.

PRESENTER: @presenter-couch is the man. Keep his face, hair, beard, watch, outfit and studio identical.

FIRST FRAME: First generate the first-frame image using @presenter-couch as the reference for the man and the studio. Image prompt: Edit the couch reference: he holds a smartphone up at arm's length with the lens facing us, as if filming the viewer, his face partly visible beside it, deadpan. The microphone stays in frame. Show it to me and check the face matches the reference (regenerate once if not). Then use it as the first frame of the clip.

CLIP 1 (10 seconds, image-to-video from the first frame):
First frame: the uploaded image. The man sits on a couch in a warm wood-slat podcast studio, holding a smartphone up as if filming.
0-3.5s SHOT 1 (A-roll, medium shot): he lowers the phone and looks into the lens: "Your supermarket does not need a video team."
3.5-5.5s SHOT 2 (A-roll, close-up): he holds up three fingers: "Film these three reels."
5.5-8.5s SHOT 3 (B-roll): a hand picking the best-looking mango from a shelf and turning it in the light. His voice continues: "One: pick the best item on the shelf,"
8.5-10s SHOT 4 (A-roll, medium shot): back to him, one nod: "and say why."

Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.

Generate only this clip. Do not chain or extend. Report anything wrong with the face, hands, props, lip-sync, voice or text.
```

**Step B: on the finished clip 1, click Extend clip and paste (clip 2)**

```
The scene continues without a cut. The same man: short black hair, trimmed beard and moustache, brown crew-neck sweater, black watch, sitting on a beige couch in front of a warm wood-slat wall with a green plant, a black podcast microphone on a boom arm at the right of the frame.
0-4s SHOT 1 (B-roll): a phone filming a well-lit deal display with a blank price tag and a blurred aisle sign. His voice continues: "Two: show one deal with the price and the aisle."
4-8s SHOT 2 (A-roll, medium shot): back to the man, counting on his fingers: "Three: answer a customer question standing in the store."
8-10s SHOT 3 (B-roll): a store employee answering a shopper's question in an aisle, soft focus, no speech.
Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.
```

**Step C: on the finished clip 2, click Extend clip and paste (clip 3)**

```
The scene continues without a cut. The same man: short black hair, trimmed beard and moustache, brown crew-neck sweater, black watch, sitting on a beige couch in front of a warm wood-slat wall with a green plant, a black podcast microphone on a boom arm at the right of the frame.
0-2.5s SHOT 1 (A-roll, close-up): "Keep each under thirty seconds."
2.5-4.3s SHOT 2 (B-roll): a phone recording with a generic timer icon in the corner. His voice continues: "Save this list."
4.3-7.3s SHOT 3 (A-roll, medium shot): straight to camera: "DM the word STORE"
7.3-10s SHOT 4 (A-roll, close-up): "and Zenix will review your supermarket marketing." Hold still for the final second.
Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.
```

---

# Reel 8: REPLY

Studio: office.

**Step A: paste in the Agent prompt box (clip 1)**

```
TASK: Make clip 1 of the reel "REPLY": one 10-second vertical 9:16 Gemini Omni Flash 1.1 clip with native audio.

PRESENTER: @presenter-office is the man. Keep his face, hair, beard, watch, outfit and studio identical.

FIRST FRAME: First generate the first-frame image using @presenter-office as the reference for the man and the studio. Image prompt: Edit the office reference: he sits at the marble table, his right hand hovering over a plain silver desk service bell on the table, looking into the lens with a patient, slightly bored expression. No folder. Show it to me and check the face matches the reference (regenerate once if not). Then use it as the first frame of the clip.

CLIP 1 (10 seconds, image-to-video from the first frame):
First frame: the uploaded image. The man sits at a marble table in a modern office, his hand hovering over a silver desk service bell.
0-4s SHOT 1 (A-roll, medium shot): he taps the bell on "register" and again on "nobody", looks into the lens, and says: "Your DMs are a cash register nobody is standing at."
4-6.8s SHOT 2 (B-roll): a phone with stacking notification badges, all text blurred and unreadable. His voice continues: "A shopper asks your hours, and waits."
6.8-10s SHOT 3 (A-roll, close-up): he holds up three fingers: "Set one automatic reply that does three things."

Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.

Generate only this clip. Do not chain or extend. Report anything wrong with the face, hands, props, lip-sync, voice or text.
```

**Step B: on the finished clip 1, click Extend clip and paste (clip 2)**

```
The scene continues without a cut. The same man: short black hair, trimmed beard and moustache, navy blazer over a white open-collar shirt, black watch, sitting at a marble table in a modern office with a warm lamp on the left.
0-1.5s SHOT 1 (A-roll, close-up): "Say thanks."
1.5-5.3s SHOT 2 (B-roll): a phone showing a simple generic chat with one reply bubble, text unreadable. His voice continues: "Answer the top three questions: hours, location, and offers."
5.3-7.3s SHOT 3 (A-roll, medium shot): back to the man, open hand: "Offer a human for everything else."
7.3-10s SHOT 4 (B-roll): a hand testing a chat reply on a second phone. His voice continues: "Test it from a customer's phone."
Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.
```

**Step C: on the finished clip 2, click Extend clip and paste (clip 3)**

```
The scene continues without a cut. The same man: short black hair, trimmed beard and moustache, navy blazer over a white open-collar shirt, black watch, sitting at a marble table in a modern office with a warm lamp on the left.
0-4s SHOT 1 (A-roll, close-up): "Automation handles the routine. People handle the rest."
4-5.3s SHOT 2 (B-roll): a hand sliding a blank template card across the marble table. His voice continues: "Save this template."
5.3-8.3s SHOT 3 (A-roll, medium shot): straight to camera: "DM the word REPLY"
8.3-10s SHOT 4 (A-roll, close-up): "and Zenix will review your setup." He taps the bell once and smiles. Hold still for the final second.
Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.
```

---

# Reel 9: SQUINT

Studio: couch.

**Step A: paste in the Agent prompt box (clip 1)**

```
TASK: Make clip 1 of the reel "SQUINT": one 10-second vertical 9:16 Gemini Omni Flash 1.1 clip with native audio.

PRESENTER: @presenter-couch is the man. Keep his face, hair, beard, watch, outfit and studio identical.

FIRST FRAME: First generate the first-frame image using @presenter-couch as the reference for the man and the studio. Image prompt: Edit the couch reference: he holds a large generic supermarket weekly flyer beside his face in his right hand, crowded with small red price bursts and produce photos, all text blurred and unreadable, squinting at it with one eye narrowed. The microphone stays in frame. Show it to me and check the face matches the reference (regenerate once if not). Then use it as the first frame of the clip.

CLIP 1 (10 seconds, image-to-video from the first frame):
First frame: the uploaded image. The man sits on a couch in a warm wood-slat podcast studio, holding a busy supermarket flyer beside his face, squinting at it.
0-3s SHOT 1 (A-roll, medium shot): he squints hard at the flyer, slowly lowers it, and says: "Squint at your weekly poster."
3-6.3s SHOT 2 (A-roll, close-up, raised eyebrow): "If the deal disappears, shoppers might miss it too."
6.3-8.3s SHOT 3 (B-roll): a busy generic flyer in soft focus where nothing stands out. His voice continues: "This is the squint test."
8.3-10s SHOT 4 (A-roll, medium shot): "It takes five seconds."

Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.

Generate only this clip. Do not chain or extend. Report anything wrong with the face, hands, props, lip-sync, voice or text.
```

**Step B: on the finished clip 1, click Extend clip and paste (clip 2)**

```
The scene continues without a cut. The same man: short black hair, trimmed beard and moustache, brown crew-neck sweater, black watch, sitting on a beige couch in front of a warm wood-slat wall with a green plant, a black podcast microphone on a boom arm at the right of the frame.
0-3s SHOT 1 (A-roll, medium shot): he narrows his eyes slightly at the camera: "Blur your eyes and look for three things."
3-6.5s SHOT 2 (B-roll): the same flyer heavily blurred, with three soft glowing areas where a hero deal, a price and a store name would sit. His voice continues: "The hero deal, the price, and the store name."
6.5-10s SHOT 3 (A-roll, close-up): he shrugs: "If any one vanishes, it is too small."
Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.
```

**Step C: on the finished clip 2, click Extend clip and paste (clip 3)**

```
The scene continues without a cut. The same man: short black hair, trimmed beard and moustache, brown crew-neck sweater, black watch, sitting on a beige couch in front of a warm wood-slat wall with a green plant, a black podcast microphone on a boom arm at the right of the frame.
0-3.8s SHOT 1 (A-roll, medium shot): he holds up a phone: "Make that one bigger, then test it on your phone."
3.8-6s SHOT 2 (B-roll): a hand holding a phone showing a blurred clean poster with one big deal. His voice continues: "Save this for your next poster."
6-10s SHOT 3 (A-roll, close-up): straight to camera: "DM the word POSTER and Zenix will review yours." Hold still for the final second.
Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.
```

---

# Reel 10: GROW

Studio: couch.

**Step A: paste in the Agent prompt box (clip 1)**

```
TASK: Make clip 1 of the reel "GROW": one 10-second vertical 9:16 Gemini Omni Flash 1.1 clip with native audio.

PRESENTER: @presenter-couch is the man. Keep his face, hair, beard, watch, outfit and studio identical.

FIRST FRAME: Use my attached first-frame image @grow-megaphone-frame exactly as the first frame of the clip. Do not regenerate it.

CLIP 1 (10 seconds, image-to-video from the first frame):
First frame: the uploaded image. The man sits on a couch in a warm wood-slat podcast studio with a microphone in frame, holding a small toy megaphone near his chin.
0-2.5s SHOT 1 (A-roll, medium shot, slow push-in): he brings the megaphone the last few inches toward his mouth, stops, says nothing, lowers it and sets it on the couch beside him. No sound comes from the megaphone.
2.5-4s SHOT 2 (A-roll, medium shot): straight to camera, deadpan: "Nobody follows a megaphone."
4-6.8s SHOT 3 (A-roll, close-up): "If your supermarket's page only shouts buy now,"
6.8-8.3s SHOT 4 (B-roll): a phone scrolling a feed of near-identical loud red grocery sale posts, text blurred. His voice continues: "why would anyone stay?"
8.3-10s SHOT 5 (A-roll, medium shot): he lifts three fanned cards beside his face: "Three posts, same pitch,"

Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.

Generate only this clip. Do not chain or extend. Report anything wrong with the face, hands, props, lip-sync, voice or text.
```

**Step B: on the finished clip 1, click Extend clip and paste (clip 2)**

```
The scene continues without a cut. The same man: short black hair, trimmed beard and moustache, brown crew-neck sweater, black watch, sitting on a beige couch in front of a warm wood-slat wall with a green plant, a black podcast microphone on a boom arm at the right of the frame.
0-3.3s SHOT 1 (A-roll, close-up): holding the fanned cards, he slowly shakes his head: "nothing to answer, nothing to save, nothing to share."
3.3-6.6s SHOT 2 (A-roll, medium shot): cards lowered, he leans in with an open palm: "Answer one real customer question in every sales post."
6.6-10s SHOT 3 (B-roll): two quick inserts: hands preparing fresh vegetables on a wooden board, then hands setting out a product display. His voice continues: "Show how a product is used,"
Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.
```

**Step C: on the finished clip 2, click Extend clip and paste (clip 3)**

```
The scene continues without a cut. The same man: short black hair, trimmed beard and moustache, brown crew-neck sweater, black watch, sitting on a beige couch in front of a warm wood-slat wall with a green plant, a black podcast microphone on a boom arm at the right of the frame.
0-2.2s SHOT 1 (B-roll): a friendly store employee talking to camera in a produce aisle, soft focus. His voice continues: "or let your team speak."
2.2-5s SHOT 2 (A-roll, medium shot): back to the man: "Then connect that post to a sale."
5-7.5s SHOT 3 (A-roll, medium shot): straight to camera: "DM the word GROW"
7.5-10s SHOT 4 (A-roll, close-up): "and Zenix will review your content." He smiles slightly. Hold still for the final second.
Voice: Charon, calm, warm, confident, male, deadpan delivery, the same voice as the previous clip. Lips match speech. No music.
Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic, 24fps, hard cuts between shots, no subtitles, no logos, no watermark, no readable text.
```

---

## After each reel

1. Check hands, props, face and lip-sync on every clip before extending. Extension copies mistakes.
2. Join the three clips (or download the extended file), then add captions, list cards, the 400% graphic and any other readable text in the editor.
3. If the voice still changes between clips, record or generate one clean voiceover of the script and replace the audio.
4. Turn on Instagram's AI disclosure when posting. The CEO and owner approve before anything is published.
