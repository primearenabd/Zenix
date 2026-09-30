# Zenix Reels: Clip-by-Clip Flow Prompts

Status: draft. Nothing is generated or published. Replaces the Agent and Extend method, which lost the presenter by clip 3.

---

## The method

Every clip is generated on its own, never extended or chained:
1. **Each clip gets its own first-frame image of the presenter** (same man, same studio, a pose that fits the clip's opening line). Upload it as the start frame in Flow.
2. **The video prompt does not describe the first frame again.** The first-frame image is the only source for how the man, the studio, the colors and the props look. The prompt says "start exactly from the attached image" and then only describes what happens: the shots, the actions, the lines. Each prompt ends with the same voice line naming **@Charon**.
3. **Every clip opens on the presenter** (A-roll) so the first-frame image always matches the first shot. B-roll comes after that.
4. Clips are independent, so you can run several at once and retry only the one that fails.
5. Join the three clips in the editor. Hard cuts hide small differences between clips.

Why this is safer: extension and chaining only see the previous video, so the presenter can drift by clip 3. A fresh first frame pins his face every time, and naming the same voice pins the sound. Re-describing the look in the video prompt made the model redraw the scene (different pose, colors and position), so the prompts now leave the look to the image.

**Checks:** confirm Charon appears as a voice option in your Flow screen and that typing @Charon works; if not, leave the plain "Charon" wording in the line. Keep each generation to no more than three ingredient images (one start frame is enough). If a clip fails with "Something went wrong", check credits, hard refresh in Chrome, and look in the Library. Each reel now needs 3 first-frame images and 3 generations, so check your credit balance first.

---

## Set up once

Upload and tag in Flow: `@presenter-armchair`, `@presenter-office`, `@presenter-couch` (the three studio images), plus your finished frames: `@map-frame` (phone with CLOSED listing), `@grow-megaphone-frame`, and `@grow-cards-frame` (three fanned cards).

**First-frame image block** (paste at the end of every first-frame image prompt):

```
Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```

**Voice block** (already included at the end of every video prompt):

```
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
```

**Order:** MAP, STORE, WEEK, PLAN, PREFLIGHT, PAGE, HOOKS, REPLY, SQUINT, GROW.

---

# Reel 1: MAP

Studio: armchair.

**Clip 1: first-frame image**
```
Use your finished image `@map-frame` as is.
```
**Clip 1: video prompt** (upload the first-frame image as the start frame)
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-1.8s SHOT 1 (A-roll, medium shot): deadpan, looking into the lens, he says: "Your store sign says open."
1.8-3.2s SHOT 2 (A-roll, tight close-up on the phone and his pointing finger): he taps the screen twice with his index finger and says: "Google says closed."
3.2-5s SHOT 3 (A-roll, medium shot, slight low angle): he lifts his eyebrows and tilts his head at the phone: "Guess who shoppers believe."
5-7.5s SHOT 4 (B-roll): a shopper glances at a phone outside a storefront, frowns. His voice continues: "Some won't call to check."
7.5-10s SHOT 5 (B-roll): the same shopper turns and walks away down the street at dusk. His voice continues: "They'll just go elsewhere."
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

**Clip 2: first-frame image**
```
Use the original armchair image `@presenter-armchair` as is (pen in hand, notebook on his lap).
```
**Clip 2: video prompt**
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-1.6s SHOT 1 (A-roll, medium shot): he looks into the lens and says: "Nearby shoppers can be"
1.6-4s SHOT 2 (B-roll): a car driving past a warm-lit storefront at dusk, slow tracking shot. His voice continues: "gone before they ever reach your door."
4-6.5s SHOT 3 (A-roll, medium shot): back to the man, phone lowered, a pen in his hand: "Check today's hours,"
6.5-10s SHOT 4 (B-roll): close-up of a hand ticking items on a blank list beside a generic shop door hours sign, text unreadable. His voice continues: "then weekends and holidays."
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

**Clip 3: first-frame image**
```
Edit @presenter-armchair: he sits back relaxed with his hands resting on the armchair arms, looking at the lens with a slight smile, no props. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 3: video prompt**
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-1.6s SHOT 1 (A-roll, medium shot): he looks into the lens and says: "Test your phone number,"
1.6-4s SHOT 2 (B-roll): a hand holding a phone over a generic business listing, tapping the call, directions and photos icons in turn, all text unreadable. His voice continues: "directions, and photos on a customer's phone."
4-7s SHOT 3 (A-roll, medium shot): back to the man, straight to camera: "DM the word MAP"
7-10s SHOT 4 (A-roll, close-up): he smiles slightly: "and Zenix will review your local listing." Hold still for the final second.
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

---

# Reel 2: STORE

Studio: office.

**Clip 1: first-frame image**
```
Edit @presenter-office: he sits slightly right of centre with one hand flat on the marble table and the other on the open green folder, which holds one blank white sheet. He leans in slightly and looks straight into the lens, serious and focused. Clean, empty wall to his left. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 1: video prompt** (upload the first-frame image as the start frame)
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-2.6s SHOT 1 (A-roll, medium shot): he leans in, looks into the lens, and says: "Four hundred percent. That's not a typo." He taps the table once on "typo" and points to the side.
2.6-5.4s SHOT 2 (A-roll, slow push-in, medium close-up): serious and steady: "Khaamar Baari Supermarket achieved four hundred percent revenue growth"
5.4-8.2s SHOT 3 (A-roll, close-up from a slightly different angle): "in one year while working with Zenix."
8.2-10s SHOT 4 (A-roll, medium shot): he sits back slightly and gives one small nod. No speech.
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

**Clip 2: first-frame image**
```
Edit @presenter-office: hands clasped on the marble table, the green folder closed, sitting back slightly, calm and inviting. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 2: video prompt**
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-3.5s SHOT 1 (A-roll, medium shot): calm and direct: "Specific proof builds trust, and a specific offer does too."
3.5-6.5s SHOT 2 (B-roll): a generic fresh produce display with one clearly highlighted item and a blank price card, slow drift. His voice continues: "Lead with your strongest deal."
6.5-10s SHOT 3 (B-roll): a phone recording a short vertical video of a produce display with a map pin icon in the corner. His voice continues: "Show the price and where to find the store,"
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

**Clip 3: first-frame image**
```
Edit @presenter-office: both hands flat on the marble table, leaning slightly forward, friendly, the green folder closed. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 3: video prompt**
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-1.5s SHOT 1 (A-roll, close-up): he looks into the lens and says: "in one short video."
1.5-4.5s SHOT 2 (B-roll): a phone showing a generic business listing with a map pin and opening hours, text unreadable. His voice continues: "Then make sure your Google listing matches."
4.5-7.5s SHOT 3 (A-roll, medium shot): back to the man, hands clasped, straight to camera: "DM the word STORE"
7.5-10s SHOT 4 (A-roll, close-up): calm and inviting: "and Zenix will review your supermarket marketing." Hold still for the final second.
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

---

# Reel 3: WEEK

Studio: armchair.

**Clip 1: first-frame image**
```
Edit @presenter-armchair: he sits in the armchair turned slightly toward the chalkboard behind him, a pen in his right hand pointing at the board, looking straight into the lens with a confident, slightly amused expression. No notebook. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 1: video prompt** (upload the first-frame image as the start frame)
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-3.3s SHOT 1 (A-roll, medium shot): he taps the chalkboard seven times with the pen and says, looking into the lens: "Steal this seven-day content plan for your supermarket."
3.3-5.3s SHOT 2 (B-roll): a hand unpacking fresh produce crates in a bright back room. His voice continues: "Monday, show what just arrived."
5.3-7.3s SHOT 3 (A-roll, close-up): he holds up one finger: "Tuesday, your hero deal."
7.3-10s SHOT 4 (B-roll): a store employee answering a question for a shopper in an aisle, soft focus. His voice continues: "Wednesday, answer a customer question."
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

**Clip 2: first-frame image**
```
Edit @presenter-armchair: he sits back in the armchair, relaxed, one hand raised as if counting, looking at the lens, no pen. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 2: video prompt**
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-2.5s SHOT 1 (A-roll, close-up): he looks into the lens and says: "Thursday, introduce a team member."
2.5-5s SHOT 2 (B-roll): a paper grocery bag being packed with a bundle of produce and staples on a counter. His voice continues: "Friday, a weekend bundle."
5-7.5s SHOT 3 (A-roll, medium shot): back to the man, pointing over his shoulder as if at a map: "Saturday, your hours and location."
7.5-10s SHOT 4 (B-roll): hands slicing vegetables in a bright kitchen. His voice continues: "Sunday, one simple recipe."
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

**Clip 3: first-frame image**
```
Edit @presenter-armchair: he sits back with his hands on the armchair arms, slight smile, looking at the lens. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 3: video prompt**
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-3s SHOT 1 (A-roll, medium shot): he sits back, relaxed: "This is a starter plan, not a rule."
3-5s SHOT 2 (B-roll): overhead shot of a blank weekly calendar on a desk and a hand placing seven sticky notes in a row. His voice continues: "Save this."
5-8s SHOT 3 (A-roll, medium shot): straight to camera: "DM the word GROW"
8-10s SHOT 4 (A-roll, close-up): "and Zenix will review your content." Hold still for the final second.
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

---

# Reel 4: PLAN

Studio: armchair.

**Clip 1: first-frame image**
```
Edit @presenter-armchair: he holds a smartphone at chest height in both hands, screen facing the lens, with a soft glowing orange circle on it and no text. No notebook. Deadpan look. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 1: video prompt** (upload the first-frame image as the start frame)
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-3s SHOT 1 (A-roll, wide shot): he shakes his head slowly and says: "The Boost button doesn't make a post better."
3-4.3s SHOT 2 (A-roll, close-up on his thumb and the phone): he taps the glowing button and says: "Just louder."
4.3-6.5s SHOT 3 (B-roll): a generic social post on a phone with a pulsing red glow, text unreadable. His voice continues: "Before you press it:"
6.5-10s SHOT 4 (A-roll, medium close-up): back to him, direct: "what should a stranger do next? Visit, call, or message?"
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

**Clip 2: first-frame image**
```
Edit @presenter-armchair: he holds a notebook and pen, leaning forward slightly with a thoughtful, direct expression, phone on the side table, wide framing. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 2: video prompt**
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-2s SHOT 1 (A-roll, medium shot): phone set aside, notebook and pen in his hands: "If you can't name it,"
2-5.8s SHOT 2 (B-roll): a generic vague social post on a phone held in front of a stream of anonymous people walking past. His voice continues: "you're paying to show a vague post to more strangers."
5.8-8.5s SHOT 3 (A-roll, close-up): he writes in the notebook and says: "Pick one offer, one audience, one action."
8.5-10s SHOT 4 (B-roll): overhead close-up of a pen writing three short lines in a notebook, text unreadable. No speech.
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

**Clip 3: first-frame image**
```
Edit @presenter-armchair: the notebook closed on his lap, pen in hand, relaxed with a slight smile, phone on the side table, wide framing. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 3: video prompt**
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-2s SHOT 1 (A-roll, close-up): he looks into the lens and says: "Put the offer first."
2-6.5s SHOT 2 (A-roll, medium shot): back to the man, straight to camera: "DM the word PLAN and Zenix will review it before you spend."
6.5-10s SHOT 3 (A-roll, close-up): he smiles and taps his phone with his thumb: "Then boost it." Hold still for the final second.
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

---

# Reel 5: PREFLIGHT

Studio: office.

**Clip 1: first-frame image**
```
Edit @presenter-office: he sits at the marble table holding a plain clipboard with a blank sheet showing four empty checkbox lines and no text, a pen in his right hand poised over the first line. He looks straight into the lens with a calm, serious expression. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 1: video prompt** (upload the first-frame image as the start frame)
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-3s SHOT 1 (A-roll, medium shot): he clicks the pen, ticks the first box, and says: "Pilots run a checklist before takeoff."
3-5.6s SHOT 2 (A-roll, close-up): he points the pen at the camera: "Run one before you spend on ads."
5.6-8s SHOT 3 (B-roll): a phone showing generic notification icons for a call, a booking and a sale, text unreadable. His voice continues: "One: can you track a call,"
8-10s SHOT 4 (B-roll): a hand tapping a generic booking calendar on a tablet. His voice continues: "a booking, or a sale?"
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

**Clip 2: first-frame image**
```
Edit @presenter-office: he holds the plain clipboard against his chest with a pen in his other hand, looking at the lens. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 2: video prompt**
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-1.6s SHOT 1 (A-roll, medium shot): he looks into the lens and says: "Two: does the ad"
1.6-3.3s SHOT 2 (B-roll): a generic grocery ad on a phone with one clear product and a blurred price, slow push-in. His voice continues: "promise one clear offer?"
3.3-6.6s SHOT 3 (A-roll, medium shot): back to the man, ticking the clipboard: "Three: does the landing page match that offer?"
6.6-10s SHOT 4 (B-roll): an overhead map with a circle drawn around a store pin, text unreadable. His voice continues: "Four: is your audience close enough to visit?"
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

**Clip 3: first-frame image**
```
Edit @presenter-office: the clipboard resting on the marble table in front of him, hands clasped, calm. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 3: video prompt**
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-2.5s SHOT 1 (A-roll, close-up): he shakes his head once: "Any no? Fix it first."
2.5-4s SHOT 2 (B-roll): a hand sliding the clipboard across the marble table toward the camera. His voice continues: "Save this."
4-7s SHOT 3 (A-roll, medium shot): straight to camera: "DM the word PLAN"
7-10s SHOT 4 (A-roll, close-up): he ticks the last box and smiles: "and Zenix will review yours." Hold still for the final second.
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

---

# Reel 6: PAGE

Studio: office.

**Clip 1: first-frame image**
```
Edit @presenter-office: the man sits upright at the marble table looking straight into the lens. His right hand rests on a plain, unbranded white milk carton standing on the table. The green folder sits closed to his left. Calm, composed, about to speak. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 1: video prompt** (upload the first-frame image as the start frame)
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-3.3s SHOT 1 (A-roll, medium shot): he lifts the carton on "milk" and lowers it out of frame below the table on "basement": "You wouldn't hide the milk in the basement."
3.3-5.2s SHOT 2 (A-roll, tight close-up): straight into the lens with one raised eyebrow: "Your landing page does."
5.2-7.6s SHOT 3 (B-roll): a laptop showing a deliberately cluttered generic landing page, blurred, slow push-in. His voice continues: "Someone clicked your ad for one offer,"
7.6-10s SHOT 4 (A-roll, medium shot, slight angle): dry and direct: "and now they're hunting through banners."
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

**Clip 2: first-frame image**
```
Edit @presenter-office: a closed laptop at his right, both hands on the table edge, leaning slightly forward, a hint of a smile. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 2: video prompt**
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-3s SHOT 1 (A-roll, close-up): a small shrug: "If the deal isn't obvious, they leave."
3-6.5s SHOT 2 (B-roll): a clean landing page mockup on a laptop with one big offer block at the top, all text unreadable, slow push-in. His voice continues: "Put your ad's exact offer at the top,"
6.5-10s SHOT 3 (A-roll, medium shot): he counts on his fingers: "with the price and one reason to trust you."
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

**Clip 3: first-frame image**
```
Edit @presenter-office: hands clasped on the table, sitting upright, calm, slight smile. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 3: video prompt**
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-3s SHOT 1 (A-roll, close-up): he looks into the lens and says: "Then give them one clear button."
3-7s SHOT 2 (A-roll, medium shot): back to the man, straight to camera: "DM the word PAGE and Zenix will check your ad and page together."
7-10s SHOT 3 (A-roll, close-up): he smiles slightly, holding still for the final second.
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

---

# Reel 7: HOOKS

Studio: couch.

**Clip 1: first-frame image**
```
Edit @presenter-couch: he holds a smartphone up at arm's length with the lens facing us, as if filming the viewer, his face partly visible beside it, deadpan. The microphone stays in frame. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 1: video prompt** (upload the first-frame image as the start frame)
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-3.5s SHOT 1 (A-roll, medium shot): he lowers the phone and looks into the lens: "Your supermarket does not need a video team."
3.5-5.5s SHOT 2 (A-roll, close-up): he holds up three fingers: "Film these three reels."
5.5-8.5s SHOT 3 (B-roll): a hand picking the best-looking mango from a shelf and turning it in the light. His voice continues: "One: pick the best item on the shelf,"
8.5-10s SHOT 4 (A-roll, medium shot): back to him, one nod: "and say why."
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

**Clip 2: first-frame image**
```
Edit @presenter-couch: he leans slightly forward with three fingers raised, no props, friendly. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 2: video prompt**
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-1.6s SHOT 1 (A-roll, medium shot): he looks into the lens and says: "Two: show one deal"
1.6-4s SHOT 2 (B-roll): a phone filming a well-lit deal display with a blank price tag and a blurred aisle sign. His voice continues: "with the price and the aisle."
4-8s SHOT 3 (A-roll, medium shot): back to the man, counting on his fingers: "Three: answer a customer question standing in the store."
8-10s SHOT 4 (B-roll): a store employee answering a shopper's question in an aisle, soft focus, no speech.
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

**Clip 3: first-frame image**
```
Edit @presenter-couch: he sits back relaxed with one hand open, no props. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 3: video prompt**
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-2.5s SHOT 1 (A-roll, close-up): "Keep each under thirty seconds."
2.5-4.3s SHOT 2 (B-roll): a phone recording with a generic timer icon in the corner. His voice continues: "Save this list."
4.3-7.3s SHOT 3 (A-roll, medium shot): straight to camera: "DM the word STORE"
7.3-10s SHOT 4 (A-roll, close-up): "and Zenix will review your supermarket marketing." Hold still for the final second.
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

---

# Reel 8: REPLY

Studio: office.

**Clip 1: first-frame image**
```
Edit @presenter-office: he sits at the marble table, his right hand hovering over a plain silver desk service bell on the table, looking into the lens with a patient, slightly bored expression. No folder. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 1: video prompt** (upload the first-frame image as the start frame)
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-4s SHOT 1 (A-roll, medium shot): he taps the bell on "register" and again on "nobody", looks into the lens, and says: "Your DMs are a cash register nobody is standing at."
4-6.8s SHOT 2 (B-roll): a phone with stacking notification badges, all text blurred and unreadable. His voice continues: "A shopper asks your hours, and waits."
6.8-10s SHOT 3 (A-roll, close-up): he holds up three fingers: "Set one automatic reply that does three things."
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

**Clip 2: first-frame image**
```
Edit @presenter-office: one hand resting beside a plain silver desk service bell on the marble table, a patient expression. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 2: video prompt**
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-1.5s SHOT 1 (A-roll, close-up): "Say thanks."
1.5-5.3s SHOT 2 (B-roll): a phone showing a simple generic chat with one reply bubble, text unreadable. His voice continues: "Answer the top three questions: hours, location, and offers."
5.3-7.3s SHOT 3 (A-roll, medium shot): back to the man, open hand: "Offer a human for everything else."
7.3-10s SHOT 4 (B-roll): a hand testing a chat reply on a second phone. His voice continues: "Test it from a customer's phone."
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

**Clip 3: first-frame image**
```
Edit @presenter-office: both hands on the table near the bell, looking at the lens, calm. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 3: video prompt**
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-4s SHOT 1 (A-roll, close-up): "Automation handles the routine. People handle the rest."
4-5.3s SHOT 2 (B-roll): a hand sliding a blank template card across the marble table. His voice continues: "Save this template."
5.3-8.3s SHOT 3 (A-roll, medium shot): straight to camera: "DM the word REPLY"
8.3-10s SHOT 4 (A-roll, close-up): "and Zenix will review your setup." He taps the bell once and smiles. Hold still for the final second.
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

---

# Reel 9: SQUINT

Studio: couch.

**Clip 1: first-frame image**
```
Edit @presenter-couch: he holds a large generic supermarket weekly flyer beside his face in his right hand, crowded with small red price bursts and produce photos, all text blurred and unreadable, squinting at it with one eye narrowed. The microphone stays in frame. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 1: video prompt** (upload the first-frame image as the start frame)
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-3s SHOT 1 (A-roll, medium shot): he squints hard at the flyer, slowly lowers it, and says: "Squint at your weekly poster."
3-6.3s SHOT 2 (A-roll, close-up, raised eyebrow): "If the deal disappears, shoppers might miss it too."
6.3-8.3s SHOT 3 (B-roll): a busy generic flyer in soft focus where nothing stands out. His voice continues: "This is the squint test."
8.3-10s SHOT 4 (A-roll, medium shot): "It takes five seconds."
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

**Clip 2: first-frame image**
```
Edit @presenter-couch: he narrows his eyes slightly and leans toward the camera, no props. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 2: video prompt**
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-3s SHOT 1 (A-roll, medium shot): he narrows his eyes slightly at the camera: "Blur your eyes and look for three things."
3-6.5s SHOT 2 (B-roll): the same flyer heavily blurred, with three soft glowing areas where a hero deal, a price and a store name would sit. His voice continues: "The hero deal, the price, and the store name."
6.5-10s SHOT 3 (A-roll, close-up): he shrugs: "If any one vanishes, it is too small."
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

**Clip 3: first-frame image**
```
Edit @presenter-couch: he holds a smartphone at chest height with the screen off, looking at the lens. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 3: video prompt**
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-3.8s SHOT 1 (A-roll, medium shot): he holds up a phone: "Make that one bigger, then test it on your phone."
3.8-6s SHOT 2 (B-roll): a hand holding a phone showing a blurred clean poster with one big deal. His voice continues: "Save this for your next poster."
6-10s SHOT 3 (A-roll, close-up): straight to camera: "DM the word POSTER and Zenix will review yours." Hold still for the final second.
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

---

# Reel 10: GROW

Studio: couch. Note: if the card lift at the end of clip 1 looks wrong, end clip 1 after 'why would anyone stay?' and open clip 2 with 'Three posts, same pitch,' before its first line.

**Clip 1: first-frame image**
```
Use your finished megaphone image `@grow-megaphone-frame` as is.
```
**Clip 1: video prompt** (upload the first-frame image as the start frame)
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-2.5s SHOT 1 (A-roll, medium shot, slow push-in): he brings the megaphone the last few inches toward his mouth, stops, says nothing, lowers it and sets it on the couch beside him. No sound comes from the megaphone.
2.5-4s SHOT 2 (A-roll, medium shot): straight to camera, deadpan: "Nobody follows a megaphone."
4-6.8s SHOT 3 (A-roll, close-up): "If your supermarket's page only shouts buy now,"
6.8-8.3s SHOT 4 (B-roll): a phone scrolling a feed of near-identical loud red grocery sale posts, text blurred. His voice continues: "why would anyone stay?"
8.3-10s SHOT 5 (A-roll, medium shot): he lifts three fanned cards beside his face: "Three posts, same pitch,"
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

**Clip 2: first-frame image**
```
Use your finished three-card image `@grow-cards-frame` as is.
```
**Clip 2: video prompt**
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-3.3s SHOT 1 (A-roll, close-up): holding the fanned cards, he slowly shakes his head: "nothing to answer, nothing to save, nothing to share."
3.3-6.6s SHOT 2 (A-roll, medium shot): cards lowered, he leans in with an open palm: "Answer one real customer question in every sales post."
6.6-10s SHOT 3 (B-roll): two quick inserts: hands preparing fresh vegetables on a wooden board, then hands setting out a product display. His voice continues: "Show how a product is used,"
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

**Clip 3: first-frame image**
```
Edit @presenter-couch: he leans slightly toward the camera with a relaxed explaining gesture, no props. Vertical 9:16, 1080x1920, photorealistic. The man must match the reference image exactly: same face, hair, beard, watch. Keep the studio, lighting and outfit from the reference. Same camera distance, eye-level, warm cinematic lighting, shallow depth of field, natural skin texture. No text, no logos, no watermark, no extra fingers, no extra people.
```
**Clip 3: video prompt**
```
Start exactly from the attached image. Keep the man, his pose, the framing, lighting, colors, background and any props exactly as in the image for the first A-roll shot, and do not redescribe or restyle them. He keeps looking at the camera unless a shot says otherwise.
0-2.2s SHOT 1 (A-roll, close-up): he looks into the lens and says: "or let your team speak."
2.2-5s SHOT 2 (A-roll, medium shot): back to the man: "Then connect that post to a sale."
5-7.5s SHOT 3 (A-roll, medium shot): straight to camera: "DM the word GROW"
7.5-10s SHOT 4 (A-roll, close-up): "and Zenix will review your content." He smiles slightly. Hold still for the final second.
Voice: @Charon (the Charon voice), calm, warm, confident, male, deadpan delivery, the same voice in every clip. Lips match speech. No music.
Vertical 9:16, hard cuts between shots, no subtitles, no logos, no watermark, no readable text. B-roll shots are realistic and match the warm look of the A-roll.
```

---

## After each reel

1. Check face, hands, props, lip-sync and voice on every clip before moving on.
2. Join the three clips and add captions, list cards, the 400% graphic and any other readable text in the editor.
3. If the voice still differs between clips, record or generate one clean voiceover of the script and replace the audio.
4. Turn on Instagram's AI disclosure when posting. The CEO and owner approve before anything is published.
