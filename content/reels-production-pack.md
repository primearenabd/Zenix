# Zenix Reels: Production Pack v2 (Google Flow + Omni Flash 1.1)

Goal: 10 reels ready to post. Each reel is about 30 seconds: three 10-second clips. Shots change every 2 to 4 seconds (A-roll = presenter, B-roll = cutaway).
Status: draft for CEO and owner approval. Nothing here is generated or published.

---

## 1. How each reel is built in Flow

| Step | What you do | Notes |
|---|---|---|
| Clip 1 | Image-to-video with the reel's first-frame image. Model: Gemini Omni Flash 1.1. 9:16, 10 seconds, audio on. Paste the clip 1 prompt plus the voice block and style block. | Only clip 1 needs a first-frame image. |
| Clip 2 | **Extend** clip 1 by 10 seconds. Paste the clip 2 prompt plus the voice block. | Omni reads the previous 10 seconds, so face, studio and voice should carry over. |
| Clip 3 | **Extend** clip 2 by 10 seconds. Paste the clip 3 prompt plus the voice block. | Result is one continuous 30-second file. |

Facts from public sources: Omni 1.1 Flash makes 3 to 10 second clips with native audio, can extend in 10-second steps up to 40 seconds, and uses the previous 10 seconds as context. Flow access depends on your Google AI plan. I could not open Google's own documentation, so confirm the exact button names for "Extend" and image-to-video in your Flow screen.
Fallback if Extend is missing: export the last frame of the previous clip, use it as the first frame of the next clip, and add the last 3 seconds of the previous clip as a reference video if Flow allows it.

## 2. Shared blocks (paste at the end of every clip prompt)

**Voice block** (Omni generates the voice itself, so there is no voice picker):
> Only the presenter's voice, no music, no background score. A calm, warm, confident adult male voice, clear natural English, steady pace, dry deadpan delivery, the same voice as the previous clip. His lips match every spoken line exactly.

**Style block:**
> Vertical 9:16, warm cinematic interior lighting, shallow depth of field, photorealistic skin and natural hand movement, 24fps. Hard cuts between shots. No subtitles, no logos, no watermark. No readable text anywhere except what is in the first-frame image.

**First-frame image block** (paste at the end of each first-frame image prompt; use the matching studio image as the reference, in edit mode):
> Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.

Studio references: **Couch** (brown sweater, mic, wood slats), **Office** (navy blazer, marble table, green folder), **Armchair** (cream sweater, green armchair, chalkboard).

## 3. The 10 reels at a glance

| # | Reel | Hook | Studio | Keyword | Why it gets watched and saved | Risk |
|---|---|---|---|---|---|---|
| 1 | MAP | "Your store sign says open. Google says closed. Guess who shoppers believe." | Armchair | MAP | Local fix every store owner can do today | Low |
| 2 | STORE | "Four hundred percent. That's not a typo." | Office | STORE | Approved proof plus a clear offer lesson | Low |
| 3 | WEEK | "Steal this seven-day content plan for your supermarket." | Armchair | GROW | Copyable template, the most saveable format | Low |
| 4 | PLAN | "The Boost button doesn't make a post better. Just louder." | Armchair | PLAN | Quotable line, fixes a common mistake | Low |
| 5 | PREFLIGHT | "Pilots run a checklist before takeoff. Run one before you spend on ads." | Office | PLAN | Four-point checklist people screenshot | Medium |
| 6 | PAGE | "You wouldn't hide the milk in the basement. Your landing page does." | Office | PAGE | Memorable metaphor, instant "I do that" moment | Medium |
| 7 | HOOKS | "Your supermarket does not need a video team." | Couch | STORE | Gives owners three shots to film this week | Medium |
| 8 | REPLY | "Your DMs are a cash register nobody is standing at." | Office | REPLY | Copy-paste auto-reply template | Medium |
| 9 | SQUINT | "Squint at your weekly poster. If the deal disappears, shoppers might miss it too." | Couch | POSTER | Five-second test people can try right now | Medium |
| 10 | GROW | "Nobody follows a megaphone." | Couch | GROW | Shareable contrarian line, prop joke | High |

Six of ten are supermarket-first (MAP, STORE, WEEK, HOOKS, SQUINT, GROW). Reel 8 (REPLY) is the AI automation demonstration, with a human handoff. Reels 4, 5 and 6 are broad marketing education for reach.

**Generate in this order (lowest risk first):** MAP, STORE, WEEK, PLAN, PREFLIGHT, PAGE, HOOKS, REPLY, SQUINT, GROW.

## 4. Two-hour schedule (realistic)

That is 30 generations plus 10 first frames plus editing. Editing and retries are the bottleneck, not writing. Suggested split, ideally with a teammate editing in parallel:

| Time | Task |
|---|---|
| 0:00 to 0:15 | CEO and owner approve all 10 scripts. Generate the 10 first-frame images. |
| 0:15 to 0:50 | Generate all 10 clip 1s. Check identity, hands and props on each. |
| 0:50 to 1:25 | Extend all clip 1s into clips 2 and 3. |
| 1:25 to 2:00 | Edit: join clips, captions, on-screen cards, export. |

Honest expectation: 10 finished reels in two hours is possible only if few clips need a retry. If credits or time run short, the order above gives you the best 6 to 8 first. Check your Flow credit balance before starting.

**Saves tip:** third-party benchmarks show carousels earn much higher save rates than Reels, and template or checklist formats save best. Turn WEEK, PREFLIGHT, HOOKS and REPLY into a matching carousel too. Sources: [Socialinsider benchmarks](https://www.socialinsider.io/social-media-benchmarks/instagram), [Adpicto carousel guide](https://www.adpicto.com/en/blog/instagram-carousel-best-practices-2026).

---

# Reel 1: MAP

**Topic:** Wrong Google listing details send nearby shoppers elsewhere
**Studio:** Armchair, close framing | **Keyword:** MAP
**HOOK (spoken):** "Your store sign says open. Google says closed. Guess who shoppers believe."
**HOOK VISUAL:** He holds a phone beside his face, taps it twice on "Google says closed", then lifts his eyebrows and tilts his head at the phone on "Guess who shoppers believe".

**Full script:**
"Your store sign says open. Google says closed. Guess who shoppers believe. Some won't call to check. They'll just go elsewhere. Nearby shoppers can be gone before they ever reach your door. Check today's hours, then weekends and holidays. Test your phone number, directions, and photos on a customer's phone. DM the word MAP and Zenix will review your local listing."

**On-screen (edit):** storefront cutaway with a lit open sign at 0 to 1.8s; generic "Closed" listing mockup; end card: HOURS, WEEKENDS, HOLIDAYS, PHONE, DIRECTIONS, PHOTOS.

**First-frame image prompt:**
> Edit the armchair reference: he sits in the armchair holding a smartphone beside his face in his right hand, screen facing the lens and showing a plain glowing blank screen. No notebook or pen. Chalkboard behind him. Deadpan, one eyebrow slightly raised.

**Clip 1 (10s, image-to-video)**
```
First frame: the uploaded image. The man sits in a green armchair in front of a chalkboard in a warm study, a smartphone held beside his face.
0-1.8s SHOT 1 (A-roll, medium shot): deadpan, looking into the lens, he says: "Your store sign says open."
1.8-3.2s SHOT 2 (A-roll, tight close-up on the phone and his face): he taps the phone twice and says: "Google says closed."
3.2-5s SHOT 3 (A-roll, medium shot, slight low angle): he lifts his eyebrows and tilts his head at the phone: "Guess who shoppers believe."
5-7.5s SHOT 4 (B-roll): a shopper glances at a phone outside a storefront, frowns. His voice continues: "Some won't call to check."
7.5-10s SHOT 5 (B-roll): the same shopper turns and walks away down the street at dusk. His voice continues: "They'll just go elsewhere."
```

**Clip 2 (10s, Extend)**
```
Extend the previous clip by 10 seconds. Same man, same armchair, same voice.
0-4s SHOT 1 (B-roll): a car driving past a warm-lit storefront at dusk, slow tracking shot. His voice continues: "Nearby shoppers can be gone before they ever reach your door."
4-6.5s SHOT 2 (A-roll, medium shot): back to the man, phone lowered, a pen in his hand: "Check today's hours,"
6.5-10s SHOT 3 (B-roll): close-up of a hand ticking items on a blank list beside a generic shop door hours sign, text unreadable. His voice continues: "then weekends and holidays."
```

**Clip 3 (10s, Extend)**
```
Extend the previous clip by 10 seconds. Same man, same armchair, same voice.
0-4s SHOT 1 (B-roll): a hand holding a phone over a generic business listing, tapping the call, directions and photos icons in turn, all text unreadable. His voice continues: "Test your phone number, directions, and photos on a customer's phone."
4-7s SHOT 2 (A-roll, medium shot): back to the man, straight to camera: "DM the word MAP"
7-10s SHOT 3 (A-roll, close-up): he smiles slightly: "and Zenix will review your local listing." Hold still for the final second.
```

---

# Reel 2: STORE

**Topic:** Approved proof from Khaamar Baari Supermarket, then how a clear offer works
**Studio:** Office | **Keyword:** STORE
**HOOK (spoken):** "Four hundred percent. That's not a typo."
**HOOK VISUAL:** He leans in with one hand flat on the table, taps the table once and points to the side on "not a typo". The "400%" count-up (0 to 400%) is added in the edit in the clean wall space, present from the first frame.

**Full script:**
"Four hundred percent. That's not a typo. Khaamar Baari Supermarket achieved four hundred percent revenue growth in one year while working with Zenix. Specific proof builds trust, and a specific offer does too. Lead with your strongest deal. Show the price and where to find the store, in one short video. Then make sure your Google listing matches. DM the word STORE and Zenix will review your supermarket marketing."

**Proof rules:** The approved sentence is spoken unchanged. No other figures. Do not say Zenix alone caused the growth. The tips are general advice, not a description of what was done for the client. Generic b-roll is never labelled as Khaamar Baari. Use real client footage only with their approval, only on the segment naming them.

**First-frame image prompt:**
> Edit the office reference: he sits slightly right of centre with one hand flat on the marble table and the other on the open green folder, which holds one blank white sheet. He leans in slightly and looks straight into the lens, serious and focused. Clean, empty wall to his left.

**Clip 1 (10s, image-to-video)**
```
First frame: the uploaded image. The man sits slightly right of centre at a marble table in a modern office, one hand flat on the table, the other on an open green folder, clean empty wall to his left.
0-2.6s SHOT 1 (A-roll, medium shot): he leans in, looks into the lens, and says: "Four hundred percent. That's not a typo." He taps the table once on "typo" and points to the side.
2.6-5.4s SHOT 2 (A-roll, slow push-in, medium close-up): serious and steady: "Khaamar Baari Supermarket achieved four hundred percent revenue growth"
5.4-8.2s SHOT 3 (A-roll, close-up from a slightly different angle): "in one year while working with Zenix."
8.2-10s SHOT 4 (A-roll, medium shot): he sits back slightly and gives one small nod. No speech.
```

**Clip 2 (10s, Extend)**
```
Extend the previous clip by 10 seconds. Same man, same office, same voice.
0-3.5s SHOT 1 (A-roll, medium shot): calm and direct: "Specific proof builds trust, and a specific offer does too."
3.5-6.5s SHOT 2 (B-roll): a generic fresh produce display with one clearly highlighted item and a blank price card, slow drift. His voice continues: "Lead with your strongest deal."
6.5-10s SHOT 3 (B-roll): a phone recording a short vertical video of a produce display with a map pin icon in the corner. His voice continues: "Show the price and where to find the store,"
```

**Clip 3 (10s, Extend)**
```
Extend the previous clip by 10 seconds. Same man, same office, same voice.
0-1.5s SHOT 1 (B-roll): the phone video continues, close-up. His voice continues: "in one short video."
1.5-4.5s SHOT 2 (B-roll): a phone showing a generic business listing with a map pin and opening hours, text unreadable. His voice continues: "Then make sure your Google listing matches."
4.5-7.5s SHOT 3 (A-roll, medium shot): back to the man, hands clasped, straight to camera: "DM the word STORE"
7.5-10s SHOT 4 (A-roll, close-up): calm and inviting: "and Zenix will review your supermarket marketing." Hold still for the final second.
```

---

# Reel 3: WEEK

**Topic:** A seven-day content plan a supermarket can copy
**Studio:** Armchair | **Keyword:** GROW
**HOOK (spoken):** "Steal this seven-day content plan for your supermarket."
**HOOK VISUAL:** He taps the chalkboard behind him seven times with his pen while looking at the camera.

**Full script:**
"Steal this seven-day content plan for your supermarket. Monday, show what just arrived. Tuesday, your hero deal. Wednesday, answer a customer question. Thursday, introduce a team member. Friday, a weekend bundle. Saturday, your hours and location. Sunday, one simple recipe. This is a starter plan, not a rule. Save this. DM the word GROW and Zenix will review your content."

**On-screen (edit):** a clean 7-day list card that stays up for the last 2 seconds so people can screenshot it: MON new arrivals, TUE hero deal, WED customer question, THU team member, FRI weekend bundle, SAT hours and location, SUN simple recipe. Day labels pop in on each spoken day.

**First-frame image prompt:**
> Edit the armchair reference: he sits in the armchair turned slightly toward the chalkboard behind him, a pen in his right hand pointing at the board, looking straight into the lens with a confident, slightly amused expression. No notebook.

**Clip 1 (10s, image-to-video)**
```
First frame: the uploaded image. The man sits in a green armchair in front of a chalkboard, a pen in his hand pointed at the board.
0-3.3s SHOT 1 (A-roll, medium shot): he taps the chalkboard seven times with the pen and says, looking into the lens: "Steal this seven-day content plan for your supermarket."
3.3-5.3s SHOT 2 (B-roll): a hand unpacking fresh produce crates in a bright back room. His voice continues: "Monday, show what just arrived."
5.3-7.3s SHOT 3 (A-roll, close-up): he holds up one finger: "Tuesday, your hero deal."
7.3-10s SHOT 4 (B-roll): a store employee answering a question for a shopper in an aisle, soft focus. His voice continues: "Wednesday, answer a customer question."
```

**Clip 2 (10s, Extend)**
```
Extend the previous clip by 10 seconds. Same man, same armchair, same voice.
0-2.5s SHOT 1 (B-roll): a friendly employee in an apron smiling at the camera in an aisle. His voice continues: "Thursday, introduce a team member."
2.5-5s SHOT 2 (B-roll): a paper grocery bag being packed with a bundle of produce and staples on a counter. His voice continues: "Friday, a weekend bundle."
5-7.5s SHOT 3 (A-roll, medium shot): back to the man, pointing over his shoulder as if at a map: "Saturday, your hours and location."
7.5-10s SHOT 4 (B-roll): hands slicing vegetables in a bright kitchen. His voice continues: "Sunday, one simple recipe."
```

**Clip 3 (10s, Extend)**
```
Extend the previous clip by 10 seconds. Same man, same armchair, same voice.
0-3s SHOT 1 (A-roll, medium shot): he sits back, relaxed: "This is a starter plan, not a rule."
3-5s SHOT 2 (B-roll): overhead shot of a blank weekly calendar on a desk and a hand placing seven sticky notes in a row. His voice continues: "Save this."
5-8s SHOT 3 (A-roll, medium shot): straight to camera: "DM the word GROW"
8-10s SHOT 4 (A-roll, close-up): "and Zenix will review your content." Hold still for the final second.
```

---

# Reel 4: PLAN

**Topic:** Boosting a post does not fix a vague post
**Studio:** Armchair, wide framing | **Keyword:** PLAN
**HOOK (spoken):** "The Boost button doesn't make a post better. Just louder."
**HOOK VISUAL:** He shakes his head slowly on "better", then taps a glowing button on his phone on "louder". Edit: a volume swell rising on "louder". BOOST label added in the edit.

**Full script:**
"The Boost button doesn't make a post better. Just louder. Before you press it: what should a stranger do next? Visit, call, or message? If you can't name it, you're paying to show a vague post to more strangers. Pick one offer, one audience, one action. Put the offer first. DM the word PLAN and Zenix will review it before you spend. Then boost it."

**First-frame image prompt:**
> Edit the armchair reference to a wider framing showing the armchair, chalkboard and side table: he holds a smartphone at chest height in both hands, screen facing the lens, with a soft glowing orange circle on it and no text. No notebook. Deadpan look.

**Clip 1 (10s, image-to-video)**
```
First frame: the uploaded image. The man sits in a green armchair in a wide shot in front of a chalkboard, holding a smartphone in both hands, a soft glowing orange circle on the screen.
0-3s SHOT 1 (A-roll, wide shot): he shakes his head slowly and says: "The Boost button doesn't make a post better."
3-4.3s SHOT 2 (A-roll, close-up on his thumb and the phone): he taps the glowing button and says: "Just louder."
4.3-6.5s SHOT 3 (B-roll): a generic social post on a phone with a pulsing red glow, text unreadable. His voice continues: "Before you press it:"
6.5-10s SHOT 4 (A-roll, medium close-up): back to him, direct: "what should a stranger do next? Visit, call, or message?"
```

**Clip 2 (10s, Extend)**
```
Extend the previous clip by 10 seconds. Same man, same armchair, same voice.
0-2s SHOT 1 (A-roll, medium shot): phone set aside, notebook and pen in his hands: "If you can't name it,"
2-5.8s SHOT 2 (B-roll): a generic vague social post on a phone held in front of a stream of anonymous people walking past. His voice continues: "you're paying to show a vague post to more strangers."
5.8-8.5s SHOT 3 (A-roll, close-up): he writes in the notebook and says: "Pick one offer, one audience, one action."
8.5-10s SHOT 4 (B-roll): overhead close-up of a pen writing three short lines in a notebook, text unreadable. No speech.
```

**Clip 3 (10s, Extend)**
```
Extend the previous clip by 10 seconds. Same man, same armchair, same voice.
0-2s SHOT 1 (B-roll): close-up of the pen circling the first line in the notebook. His voice continues: "Put the offer first."
2-6.5s SHOT 2 (A-roll, medium shot): back to the man, straight to camera: "DM the word PLAN and Zenix will review it before you spend."
6.5-10s SHOT 3 (A-roll, close-up): he smiles and taps his phone with his thumb: "Then boost it." Hold still for the final second.
```

---

# Reel 5: PREFLIGHT

**Topic:** A four-point check before spending on ads
**Studio:** Office | **Keyword:** PLAN
**HOOK (spoken):** "Pilots run a checklist before takeoff. Run one before you spend on ads."
**HOOK VISUAL:** He holds a clipboard with blank checklist lines, clicks a pen and ticks the first box on "takeoff".

**Full script:**
"Pilots run a checklist before takeoff. Run one before you spend on ads. One: can you track a call, a booking, or a sale? Two: does the ad promise one clear offer? Three: does the landing page match that offer? Four: is your audience close enough to visit? Any no? Fix it first. Save this. DM the word PLAN and Zenix will review yours."

**On-screen (edit):** a checklist card that ticks each item as it is spoken: 1 TRACKING, 2 ONE CLEAR OFFER, 3 PAGE MATCHES AD, 4 AUDIENCE NEARBY. Hold the full card for the last 2 seconds for screenshots.

**First-frame image prompt:**
> Edit the office reference: he sits at the marble table holding a plain clipboard with a blank sheet showing four empty checkbox lines and no text, a pen in his right hand poised over the first line. He looks straight into the lens with a calm, serious expression.

**Clip 1 (10s, image-to-video)**
```
First frame: the uploaded image. The man sits at a marble table in a modern office holding a clipboard, a pen poised over the first checkbox.
0-3s SHOT 1 (A-roll, medium shot): he clicks the pen, ticks the first box, and says: "Pilots run a checklist before takeoff."
3-5.6s SHOT 2 (A-roll, close-up): he points the pen at the camera: "Run one before you spend on ads."
5.6-8s SHOT 3 (B-roll): a phone showing generic notification icons for a call, a booking and a sale, text unreadable. His voice continues: "One: can you track a call,"
8-10s SHOT 4 (B-roll): a hand tapping a generic booking calendar on a tablet. His voice continues: "a booking, or a sale?"
```

**Clip 2 (10s, Extend)**
```
Extend the previous clip by 10 seconds. Same man, same office, same voice.
0-3.3s SHOT 1 (B-roll): a generic grocery ad on a phone with one clear product and a blurred price, slow push-in. His voice continues: "Two: does the ad promise one clear offer?"
3.3-6.6s SHOT 2 (A-roll, medium shot): back to the man, ticking the clipboard: "Three: does the landing page match that offer?"
6.6-10s SHOT 3 (B-roll): an overhead map with a circle drawn around a store pin, text unreadable. His voice continues: "Four: is your audience close enough to visit?"
```

**Clip 3 (10s, Extend)**
```
Extend the previous clip by 10 seconds. Same man, same office, same voice.
0-2.5s SHOT 1 (A-roll, close-up): he shakes his head once: "Any no? Fix it first."
2.5-4s SHOT 2 (B-roll): a hand sliding the clipboard across the marble table toward the camera. His voice continues: "Save this."
4-7s SHOT 3 (A-roll, medium shot): straight to camera: "DM the word PLAN"
7-10s SHOT 4 (A-roll, close-up): he ticks the last box and smiles: "and Zenix will review yours." Hold still for the final second.
```

---

# Reel 6: PAGE

**Topic:** Ad clicks fail when the landing page hides the offer
**Studio:** Office | **Keyword:** PAGE
**HOOK (spoken):** "You wouldn't hide the milk in the basement. Your landing page does."
**HOOK VISUAL:** He picks up a plain milk carton on "milk", lowers it out of frame below the table on "basement", then looks into camera with one raised eyebrow on "Your landing page does". Edit: small thud when it drops.

**Full script:**
"You wouldn't hide the milk in the basement. Your landing page does. Someone clicked your ad for one offer, and now they're hunting through banners. If the deal isn't obvious, they leave. Put your ad's exact offer at the top, with the price and one reason to trust you. Then give them one clear button. DM the word PAGE and Zenix will check your ad and page together."

**First-frame image prompt:**
> Edit the office reference: the man sits upright at the marble table looking straight into the lens. His right hand rests on a plain, unbranded white milk carton standing on the table. The green folder sits closed to his left. Calm, composed, about to speak.

**Clip 1 (10s, image-to-video)**
```
First frame: the uploaded image. The man sits upright at a marble table in a modern office, his right hand resting on a plain white milk carton.
0-3.3s SHOT 1 (A-roll, medium shot): he lifts the carton on "milk" and lowers it out of frame below the table on "basement": "You wouldn't hide the milk in the basement."
3.3-5.2s SHOT 2 (A-roll, tight close-up): straight into the lens with one raised eyebrow: "Your landing page does."
5.2-7.6s SHOT 3 (B-roll): a laptop showing a deliberately cluttered generic landing page, blurred, slow push-in. His voice continues: "Someone clicked your ad for one offer,"
7.6-10s SHOT 4 (A-roll, medium shot, slight angle): dry and direct: "and now they're hunting through banners."
```

**Clip 2 (10s, Extend)**
```
Extend the previous clip by 10 seconds. Same man, same office, same voice.
0-3s SHOT 1 (A-roll, close-up): a small shrug: "If the deal isn't obvious, they leave."
3-6.5s SHOT 2 (B-roll): a clean landing page mockup on a laptop with one big offer block at the top, all text unreadable, slow push-in. His voice continues: "Put your ad's exact offer at the top,"
6.5-10s SHOT 3 (A-roll, medium shot): he counts on his fingers: "with the price and one reason to trust you."
```

**Clip 3 (10s, Extend)**
```
Extend the previous clip by 10 seconds. Same man, same office, same voice.
0-3s SHOT 1 (B-roll): a finger tapping a large green button on a clean generic page on a phone. His voice continues: "Then give them one clear button."
3-7s SHOT 2 (A-roll, medium shot): back to the man, straight to camera: "DM the word PAGE and Zenix will check your ad and page together."
7-10s SHOT 3 (A-roll, close-up): he smiles slightly, holding still for the final second.
```

---

# Reel 7: HOOKS

**Topic:** Three phone-filmable reels any supermarket can make this week
**Studio:** Couch | **Keyword:** STORE
**HOOK (spoken):** "Your supermarket does not need a video team."
**HOOK VISUAL:** He holds a phone up as if filming the viewer, then lowers it and looks into the lens.

**Full script:**
"Your supermarket does not need a video team. Film these three reels. One: pick the best item on the shelf, and say why. Two: show one deal with the price and the aisle. Three: answer a customer question standing in the store. Keep each under thirty seconds. Save this list. DM the word STORE and Zenix will review your supermarket marketing."

**On-screen (edit):** list card for screenshots: 1 BEST ITEM AND WHY, 2 ONE DEAL, PRICE, AISLE, 3 A CUSTOMER QUESTION, UNDER 30 SECONDS.

**First-frame image prompt:**
> Edit the couch reference: he holds a smartphone up at arm's length with the lens facing us, as if filming the viewer, his face partly visible beside it, deadpan. The microphone stays in frame.

**Clip 1 (10s, image-to-video)**
```
First frame: the uploaded image. The man sits on a couch in a warm wood-slat podcast studio, holding a smartphone up as if filming.
0-3.5s SHOT 1 (A-roll, medium shot): he lowers the phone and looks into the lens: "Your supermarket does not need a video team."
3.5-5.5s SHOT 2 (A-roll, close-up): he holds up three fingers: "Film these three reels."
5.5-8.5s SHOT 3 (B-roll): a hand picking the best-looking mango from a shelf and turning it in the light. His voice continues: "One: pick the best item on the shelf,"
8.5-10s SHOT 4 (A-roll, medium shot): back to him, one nod: "and say why."
```

**Clip 2 (10s, Extend)**
```
Extend the previous clip by 10 seconds. Same man, same couch, same voice.
0-4s SHOT 1 (B-roll): a phone filming a well-lit deal display with a blank price tag and a blurred aisle sign. His voice continues: "Two: show one deal with the price and the aisle."
4-8s SHOT 2 (A-roll, medium shot): back to the man, counting on his fingers: "Three: answer a customer question standing in the store."
8-10s SHOT 3 (B-roll): a store employee answering a shopper's question in an aisle, soft focus, no speech.
```

**Clip 3 (10s, Extend)**
```
Extend the previous clip by 10 seconds. Same man, same couch, same voice.
0-2.5s SHOT 1 (A-roll, close-up): "Keep each under thirty seconds."
2.5-4.3s SHOT 2 (B-roll): a phone recording with a generic timer icon in the corner. His voice continues: "Save this list."
4.3-7.3s SHOT 3 (A-roll, medium shot): straight to camera: "DM the word STORE"
7.3-10s SHOT 4 (A-roll, close-up): "and Zenix will review your supermarket marketing." Hold still for the final second.
```

---

# Reel 8: REPLY

**Topic:** One automatic DM reply with a human handoff
**Studio:** Office | **Keyword:** REPLY
**HOOK (spoken):** "Your DMs are a cash register nobody is standing at."
**HOOK VISUAL:** A silver desk service bell sits on the table. He taps it on "cash register", taps it again on "nobody", then looks into the lens and waits. Edit: two bell dings.

**Full script:**
"Your DMs are a cash register nobody is standing at. A shopper asks your hours, and waits. Set one automatic reply that does three things. Say thanks. Answer the top three questions: hours, location, and offers. Offer a human for everything else. Test it from a customer's phone. Automation handles the routine. People handle the rest. Save this template. DM the word REPLY and Zenix will review your setup."

**On-screen (edit):** template card for screenshots: 1 THANK THEM, 2 HOURS, LOCATION, OFFERS, 3 OFFER A HUMAN. Use no real customer data anywhere.

**First-frame image prompt:**
> Edit the office reference: he sits at the marble table, his right hand hovering over a plain silver desk service bell on the table, looking into the lens with a patient, slightly bored expression. No folder.

**Clip 1 (10s, image-to-video)**
```
First frame: the uploaded image. The man sits at a marble table in a modern office, his hand hovering over a silver desk service bell.
0-4s SHOT 1 (A-roll, medium shot): he taps the bell on "register" and again on "nobody", looks into the lens, and says: "Your DMs are a cash register nobody is standing at."
4-6.8s SHOT 2 (B-roll): a phone with stacking notification badges, all text blurred and unreadable. His voice continues: "A shopper asks your hours, and waits."
6.8-10s SHOT 3 (A-roll, close-up): he holds up three fingers: "Set one automatic reply that does three things."
```

**Clip 2 (10s, Extend)**
```
Extend the previous clip by 10 seconds. Same man, same office, same voice.
0-1.5s SHOT 1 (A-roll, close-up): "Say thanks."
1.5-5.3s SHOT 2 (B-roll): a phone showing a simple generic chat with one reply bubble, text unreadable. His voice continues: "Answer the top three questions: hours, location, and offers."
5.3-7.3s SHOT 3 (A-roll, medium shot): back to the man, open hand: "Offer a human for everything else."
7.3-10s SHOT 4 (B-roll): a hand testing a chat reply on a second phone. His voice continues: "Test it from a customer's phone."
```

**Clip 3 (10s, Extend)**
```
Extend the previous clip by 10 seconds. Same man, same office, same voice.
0-4s SHOT 1 (A-roll, close-up): "Automation handles the routine. People handle the rest."
4-5.3s SHOT 2 (B-roll): a hand sliding a blank template card across the marble table. His voice continues: "Save this template."
5.3-8.3s SHOT 3 (A-roll, medium shot): straight to camera: "DM the word REPLY"
8.3-10s SHOT 4 (A-roll, close-up): "and Zenix will review your setup." He taps the bell once and smiles. Hold still for the final second.
```

---

# Reel 9: SQUINT

**Topic:** A five-second squint test for weekly posters
**Studio:** Couch | **Keyword:** POSTER
**HOOK (spoken):** "Squint at your weekly poster. If the deal disappears, shoppers might miss it too."
**HOOK VISUAL:** He holds a busy generic supermarket poster beside his face and squints dramatically at it, then slowly lowers it to look into the lens with a raised eyebrow.

**Full script:**
"Squint at your weekly poster. If the deal disappears, shoppers might miss it too. This is the squint test. It takes five seconds. Blur your eyes and look for three things. The hero deal, the price, and the store name. If any one vanishes, it is too small. Make that one bigger, then test it on your phone. Save this for your next poster. DM the word POSTER and Zenix will review yours."

**On-screen (edit):** end card for screenshots: SQUINT TEST, 1 HERO DEAL, 2 PRICE, 3 STORE NAME. Highlight boxes appear over the blurred poster.

**First-frame image prompt:**
> Edit the couch reference: he holds a large generic supermarket weekly flyer beside his face in his right hand, crowded with small red price bursts and produce photos, all text blurred and unreadable, squinting at it with one eye narrowed. The microphone stays in frame.

**Clip 1 (10s, image-to-video)**
```
First frame: the uploaded image. The man sits on a couch in a warm wood-slat podcast studio, holding a busy supermarket flyer beside his face, squinting at it.
0-3s SHOT 1 (A-roll, medium shot): he squints hard at the flyer, slowly lowers it, and says: "Squint at your weekly poster."
3-6.3s SHOT 2 (A-roll, close-up, raised eyebrow): "If the deal disappears, shoppers might miss it too."
6.3-8.3s SHOT 3 (B-roll): a busy generic flyer in soft focus where nothing stands out. His voice continues: "This is the squint test."
8.3-10s SHOT 4 (A-roll, medium shot): "It takes five seconds."
```

**Clip 2 (10s, Extend)**
```
Extend the previous clip by 10 seconds. Same man, same couch, same voice.
0-3s SHOT 1 (A-roll, medium shot): he narrows his eyes slightly at the camera: "Blur your eyes and look for three things."
3-6.5s SHOT 2 (B-roll): the same flyer heavily blurred, with three soft glowing areas where a hero deal, a price and a store name would sit. His voice continues: "The hero deal, the price, and the store name."
6.5-10s SHOT 3 (A-roll, close-up): he shrugs: "If any one vanishes, it is too small."
```

**Clip 3 (10s, Extend)**
```
Extend the previous clip by 10 seconds. Same man, same couch, same voice.
0-3.8s SHOT 1 (A-roll, medium shot): he holds up a phone: "Make that one bigger, then test it on your phone."
3.8-6s SHOT 2 (B-roll): a hand holding a phone showing a blurred clean poster with one big deal. His voice continues: "Save this for your next poster."
6-10s SHOT 3 (A-roll, close-up): straight to camera: "DM the word POSTER and Zenix will review yours." Hold still for the final second.
```

---

# Reel 10: GROW

**Topic:** Sales-only posts lose followers; what to post instead
**Studio:** Couch | **Keyword:** GROW
**HOOK (spoken):** "Nobody follows a megaphone."
**HOOK VISUAL:** He brings a toy megaphone toward his mouth, stops, says nothing, lowers it and sets it aside, then delivers the line deadpan. The megaphone makes no sound.

**Full script:**
"Nobody follows a megaphone. If your supermarket's page only shouts buy now, why would anyone stay? Three posts, same pitch, nothing to answer, nothing to save, nothing to share. Answer one real customer question in every sales post. Show how a product is used, or let your team speak. Then connect that post to a sale. DM the word GROW and Zenix will review your content."

**First frames:** you already have two: the megaphone frame (use for clip 1) and the three-card frame. In this 10-second version the cards appear at the end of clip 1, so you only need the megaphone frame. If the megaphone to cards swap looks wrong, generate the cards beat from your card frame as a separate 4-second clip and cut it in.

**Clip 1 (10s, image-to-video)**
```
First frame: the uploaded image. The man sits on a couch in a warm wood-slat podcast studio with a microphone in frame, holding a small toy megaphone near his chin.
0-2.5s SHOT 1 (A-roll, medium shot, slow push-in): he brings the megaphone the last few inches toward his mouth, stops, says nothing, lowers it and sets it on the couch beside him. No sound comes from the megaphone.
2.5-4s SHOT 2 (A-roll, medium shot): straight to camera, deadpan: "Nobody follows a megaphone."
4-6.8s SHOT 3 (A-roll, close-up): "If your supermarket's page only shouts buy now,"
6.8-8.3s SHOT 4 (B-roll): a phone scrolling a feed of near-identical loud red grocery sale posts, text blurred. His voice continues: "why would anyone stay?"
8.3-10s SHOT 5 (A-roll, medium shot): he lifts three fanned cards beside his face: "Three posts, same pitch,"
```

**Clip 2 (10s, Extend)**
```
Extend the previous clip by 10 seconds. Same man, same couch, same voice.
0-3.3s SHOT 1 (A-roll, close-up): holding the fanned cards, he slowly shakes his head: "nothing to answer, nothing to save, nothing to share."
3.3-6.6s SHOT 2 (A-roll, medium shot): cards lowered, he leans in with an open palm: "Answer one real customer question in every sales post."
6.6-10s SHOT 3 (B-roll): two quick inserts: hands preparing fresh vegetables on a wooden board, then hands setting out a product display. His voice continues: "Show how a product is used,"
```

**Clip 3 (10s, Extend)**
```
Extend the previous clip by 10 seconds. Same man, same couch, same voice.
0-2.2s SHOT 1 (B-roll): a friendly store employee talking to camera in a produce aisle, soft focus. His voice continues: "or let your team speak."
2.2-5s SHOT 2 (A-roll, medium shot): back to the man: "Then connect that post to a sale."
5-7.5s SHOT 3 (A-roll, medium shot): straight to camera: "DM the word GROW"
7.5-10s SHOT 4 (A-roll, close-up): "and Zenix will review your content." He smiles slightly. Hold still for the final second.
```

---

## 5. Checks before you generate

1. The CEO and owner approve all 10 scripts, every hook action, and the use of his likeness and voice.
2. Timed read-through of at least two scripts: each clip holds about 20 to 25 spoken words in 10 seconds. If speech is cut off, trim the last phrase in that clip.
3. Check hands, props (milk carton, megaphone, bell, clipboard, flyer) and face on every clip 1 before extending. Extension copies mistakes.
4. All readable text (captions, list cards, the 400% graphic, BOOST, Closed, template cards) goes on in the edit, never in the video model.
5. Omni's voice may differ between reels. If it drifts inside a reel, record one clean voiceover of that reel's script and replace the audio in the edit.
6. Turn on Instagram's AI disclosure when posting. Do not publish without the owner's approval.
7. Each review offer (PAGE, GROW, STORE, MAP, PLAN, REPLY, POSTER) needs a weekly cap and an owner before it is promised on camera.

## 6. Fallbacks
- Extend unavailable: use last frame as the next first frame (see section 1).
- Prop looks wrong: drop the prop, keep the line and the facial action; build the prop beat as an edited insert.
- Face or likeness blocked: tell me the exact error and I will rework the frames.
- Speech rushed: drop a clause or make that clip prompt say "slow, measured pace".
