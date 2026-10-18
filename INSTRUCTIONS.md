# How to Make an "iPhone"-Style Product Video of Yourself

Oct 18, 2026 · @Lingjie Feng

Introduce yourself the way Apple introduces a product: one serious grey studio, short spec-style captions, a lineup of your "models", and a white title card.

## What you need

1. Editing tools. I recommend using claude code or codex for vibe editing. I used claude code opus 5.5 for my iFeng video.
2. A video generation platform (so you don't have to pay for photography studio): I used Seedance 2.0 model from Higgsfield.
   1. To make sure the characters in the video look exactly like you, prepare five clear photos of your face, the reference video(you can take my video as reference cut).

More specifically:

| Tool | Used for | Comment |
| --- | --- | --- |
| Higgsfield, **Seedance 2.0** model | Generating every shot of you | 720p works okay, but 1080p is better |
| Higgsfield **Bytedance Video Upscale** (standard, AIGC preset) | Sharpening the takes you keep | If the generated video is a bit blur, use this to boost the quality |
| Higgsfield CLI (optional) | Scripting many generations | If you don't want to put prompt manually on the Higgsfield platform, you can make claude code or codex do it for you through Higgsfield's official cli |
| Five face photos | Keeping your face consistent across shots |  |
| The reference video (iFeng) | Timing, cut points and the soundtrack |  |
| An editor: Claude Code/Codex + the Remotion library | Cutting, captions, the lineup and close-ups |  |
| ffmpeg (optional) | Trimming, extracting the music, grabbing frames |  |

## Step 1 — Storyboard the beats to the music

The soundtrack sets the edit: every cut lands on a strong hit in the music.

You can just ask Claude code or Codex to analyze the Storyboard of my video and apply it to your video. Then you can prompt for followup changes so it actually matches your life and your story.

In this step, we are not generating anything yet!

Review the proposed storyboard of your video to see what are the clips that requires video generation.

## Step 3 — Prompt templates

For those clips that require video generation, you need to have prompts to generate high quality videos.

[the prompts I used to generate all footages of my video is in Appendix below. Feel free to change them so it matches your version.]

Every prompt is built from the same blocks in the same order: **Scene → Face → Outfit → (Framing) → Action, second by second → Closing.** Keeping Scene and Closing word-for-word identical is what makes 12 separate clips look like one shoot. Replace everything in [brackets].

## Step 4 — Generate and review

Once you have those prompts,  you can start generating videos using any video generation platform.

## Step 5 — Edit

Never edit it yourself! That will be a week of work.

Instead, just take a look at the first auto-cut result and prompt the claude code or codex to make changes.

## Step 6 — Finish and post

Yeah!

## Appendix

### Shared blocks

Scene (every shot):

```
Premium minimalist technology product commercial in the style of an Apple product film. Seamless light-gray studio cyclorama with no visible horizon line, soft diffused overhead key light slightly from the front-left, a soft natural shadow on the floor, empty space, no props except those described.
```

Face (every shot):

```
The subject is the person shown in the reference images. Use the reference images ONLY for their face, facial proportions, natural skin tone and texture, and hair; ignore the clothing in them. Natural minimal makeup.
```

Outfit (one per shot, always in words):

```
They wear [garment by garment: colour, fabric, cut — e.g. a black sleeveless ribbed mock-neck knit top tucked into high-waisted taupe wide-leg trousers, a thin black belt and black flats]. Their hair is [down / in a high ponytail].
```

Closing (every shot):

```
Photorealistic, natural subtle motion, neutral muted color, clean and serious product-film tone. No speech, no lip movement, no captions, no text, no logos, no brand marks, no watermarks, no other people.
```

Framing (the five lineup modes only — identical framing is what lets you line them up later):

```
The camera lens sits level with their chest, 50mm. It starts on a wide full-body framing and stays perfectly still until the push-in described below. They stand exactly centered horizontally, facing the camera: the top of their head at about 15% from the top of the frame and their feet at about 90%, with even empty gray space on both sides.
```

### Action block per shot

**Back reveal** (5 s):

```
0-2s: tight shot from directly behind them, centered: shoulders and hair fill the frame, perfectly still, presented like a product seen from the back. Very slow push-in.
2-5s: the camera glides smoothly backward to a centered medium-wide shot of them standing upright in the gray void, still facing away. In the last second they turn their head slightly over their shoulder, showing their profile, calm and composed.
```

**Curiosity sensors** (5 s; we used only the final face shot):

```
Tight close-up of their face, eyes in crisp focus, very shallow depth of field. They look attentively toward something just outside the frame on the left, then their eyes shift slightly as if they have detected something interesting. Calm, intelligent expression.
```

**Your field** (5 s; ours was AI × silicon — change the screen contents to your work):

```
They stand centered, head to mid-thigh, inside a wide semicircular arc of floating frosted-glass screens at different depths, some behind them, some in front at the sides. The screens clearly show [three themes, e.g. chip die and block diagram · code and training logs scrolling · a node graph of AI agents]. The camera slowly pushes in; the panels drift gently. They raise their right hand and lightly touch the panel at upper right, which brightens, while their left hand gestures toward the panel at lower left. Calm, focused, no big smile.
```

**What you make** (5 s; ours: explaining things on camera):

```
0-2s: medium close-up facing the lens, explaining something warmly with small open hand gestures at chest height.
2-5s: the camera glides backward and slightly sideways to reveal they are being filmed: a black cinema camera on a tripod in the soft-focus foreground, its monitor showing them; a tall softbox; a boom mic just out of their frame. They keep explaining throughout.
```

**Overheating** (5 s; use the first ~2 s):

```
They sit at a minimal white desk with a silver laptop. Front medium close-up. They stare at the screen with intense, unblinking concentration, brow slightly furrowed, the screen glow on their face. Very slow push-in.
```

**Touch grass** (4 s; your sport):

```
Camera locked, full body slightly left of center, standing sideways facing screen right in a ready stance.
0-1s: a bright yellow tennis ball flies in fast from the right edge of the frame.
1-2s: they step into a clean, powerful forehand and strike the ball at waist height; the ball fires back out of frame to the right.
2-4s: a full follow-through, then they relax and look toward camera with a small, satisfied smile.
```

**Mode clips** (four at 4 s, the Creator at 5 s). Each: 2 s standing perfectly still at full body (for the lineup), then a push-in **that ends head-to-hips with clear headroom** while they do one small signature action.

```
0-2s (camera still, full body): they stand perfectly still, feet together, arms relaxed, composed neutral expression, looking into the lens.
2-4s (smooth push-in): the camera glides smoothly forward from full body to a medium shot framed from a little above the top of their head down to their hips, keeping clear headroom the whole time, while they [action].
```

Actions we used: Engineer — types fast on an invisible keyboard floating at chest height · Researcher (with round wire glasses) — traces a line on an invisible diagram, hand at chin · Athlete — flips the racket up onto their shoulder · Off-duty — one happy 360° twirl, ending on a big smile.

**Creator = the walk-in** (5 s). The centre of the lineup is the person who walks in, so this one clip does both jobs:

```
0-1.6s (camera still, full body): they walk a few slow, graceful steps straight toward the camera, centered, like a product gliding into view.
1.6-2s: they stop, feet together, exactly centered.
2-3.4s: they stand perfectly still, looking into the lens.
3.4-5s (smooth push-in to chest-up): they lift a black handheld microphone to just below their chin and settle into a confident half-smile, lips closed.
```
