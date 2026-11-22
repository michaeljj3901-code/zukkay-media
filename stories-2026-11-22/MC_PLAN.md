# MC_PLAN · Story batch Nov 22, 2026 (REVIEW ONLY, nothing scheduled)

Standing playbook: /home/box/shared/skills/ZUKKAY_CONTENT_VISION.md (Michael, Nov 22). Zukkay rules beat the skills: price + LINK IN BIO on screen from frame 1, no comment-keyword CTAs, FB on every post, no em dashes, AI-tells check, 5-tag captions with 30/18 alternates, GTA/PS5 disclaimer, 1080x1920, -14 LUFS, vault audio rotation logged.

## Priors from data/viral_metrics.csv (62 rows with views; our median = 140 views)
- hook_type medians: problem_benefit 160 (max 2,564), curiosity_mood 160 (max 776), price_first 144, identity_nurse 132, brand_ugc 115.
- format medians: ai_animated_photo 374 (max 2,564) > real_video_optimized 149 > photo_kenburns 139 > real_video_asis 128. ai_vs_real: ai 374 vs real 139.
- best slots (median views): sun 14-17 1,910 (n=1), wed 11-14 778, wed 14-17 602, sat 14-17 500 (n=1), fri 20-24 452, tue 17-20 167 (n=9, holds the 2,564 max).
- Not in the CSV yet: Skull "Park your controller here." ~5.4K to 7.6K IG views (best ever, curiosity/parking hook).
- Caveat: small n per cell, so these are priors, not proof. Re-score weekly against our own median.

## Arms this cycle (6 posts: 4 exploit = 67%, 2 explore = 33%, nearest split to 70/30 at n=6)
Exploit = hook_type AND slot drawn from the winners above. Explore = new hook type (pov_skit) and an untested/low-data slot. The story format itself is new for every variant (format exploration is built in), and the engine mix (Higgsfield scenes + real-product composites) is new vs. MU API animated photos.

| variant | hook_type | format | tone | setting | engine | ai_vs_real | len s | audio | proposed post time (ET) | arm |
|---|---|---|---|---|---|---|---|---|---|---|
| WALL_A_sarcastic-journey | curiosity_mood | story_purchase_journey | sarcastic | phone>doorstep>living-room neon wall | higgsfield gpt_image_2+soul_2+kling3_0 / ffmpeg composite | hybrid | 16.2 | snd-0011 @2s | Fri Nov 27 8:30 PM ET (fri 20-24) | EXPLOIT (winner hook family + top slot) |
| WALL_B_deadpan-pov | pov_skit | story_reveal_then_flashback | deadpan POV | neon wall first, then journey steps | higgsfield gpt_image_2+soul_2+kling3_0 / ffmpeg composite | hybrid | 15.6 | snd-0012 @6s | Mon Nov 30 8:00 PM ET (mon 20-24) | EXPLORE (new hook type + untested slot) |
| WALL_C_hype-blank-wall | problem_benefit | story_lights_off_on_reveal | hype | dark wall lights-on reveal, then journey | higgsfield gpt_image_2+soul_2+kling3_0 / ffmpeg composite | hybrid | 15.4 | snd-0010 @0s | Sun Nov 29 2:30 PM ET (sun 14-17) | EXPLOIT (top hook type + top slot) |
| PS5_A_sarcastic-couch | problem_benefit | story_problem_to_desk | sarcastic | couch cushions > neon gaming desk with AI gamer | higgsfield gpt_image_2+soul_2+kling3_0 / ffmpeg composite | hybrid | 14.2 | snd-0012 @0s | Tue Nov 24 7:30 PM ET (tue 17-20) | EXPLOIT (top hook type + top slot) |
| PS5_B_funny-pov-player2 | pov_skit | story_desk_in_use | funny POV | neon gaming desk, AI gamer playing, holder on desk | higgsfield soul_2+kling3_0+gpt_image_2 / ffmpeg composite | hybrid | 14.7 | snd-0011 @4s | Thu Nov 26 8:30 PM ET (thu 20-24) | EXPLORE (new hook type + low-data slot) |
| PS5_C_hype-countdown | curiosity_mood | before_after_countdown | hype | dark desk 3-2-1 > lit neon desk | higgsfield gpt_image_2+soul_2+kling3_0 / ffmpeg composite | hybrid | 13.5 | snd-0010 @3s | Sat Nov 28 3:00 PM ET (sat 14-17) | EXPLOIT (winner hook family + top slot; new countdown format) |

Spacing check for the proposed times: none within 6h of SKULL_D (Mon 11/23 9 AM), REEL_1 (Mon 11/23 5:30 PM) or REEL_2 (Wed 11/25 2:30 PM). PS5_A Tue 7:30 PM sits 1.5h after the held nurse draft at Tue 6 PM (different niche; move to 8:30 PM if the nurse posts get released). Nothing on Wed 11/25. Black Friday evening (Fri 11/27 8:30 PM) goes to WALL_A.

## Routing (spread the load)
- Generation used this cycle: Higgsfield (6 GPT Image 2 scenes, 2 Soul 2 scenes, 2 Kling 3.0 5s clips) + ffmpeg/PIL composites of real product cutouts (free). MU API: none today (cap used). OpenRouter: untouched (reels-af has that $1). Canva: not needed this cycle.
- Posting route proposal after Chief review: 3 via Buffer (PS5_A, WALL_C, PS5_C) and 3 via The Coder's direct posts (WALL_A, PS5_B, WALL_B), FB on all 6. AI labels: IG + TT toggles on; FB label set in Meta Business Suite after publish.

## Measure (data/viral_metrics.csv, approved columns)
Log each post on publish with hook_type, format, tone, engine, ai_vs_real=hybrid, ai_cost_usd, then read_24h / read_7d / read_30d (views, avg watch, saves, shares, profile visits). Score = views / our median, with shares+saves as tiebreak.
Decision rule at the 7d read: an arm >= 1.5x median gets a recut in the next cycle's exploit pool; < 0.7x median retires that hook/slot combo. Next cycle keeps 70% of slots on the top-scoring combos, 30% on fresh random combos (draw hook_type, tone, setting, slot, engine at random from the untested set).

## Research inputs used
- Gaming niche: /workspace/ai-batch-1122/skull/TREND_RESEARCH.md (Trendstalkr gaming-setup posts: Before/After avg 28.7M on 3 videos, countdown hooks; "name the item first" 25x median per Volume) -> PS5_C countdown, PS5_A item-in-hook.
- Room decor: Dropified (Nov 14, 2026) LED room-transformation structure: dark before, quick install cuts, lights-on reveal, 7-10 PM peak (https://www.dropified.com/blog/led-strip-lights-on-tiktok-shop-creating-viral-room-transformation-before-after-content-that-converts-renters-gen-z-at-7/); Y SIGNS (May 2026) on layered neon + art walls (https://www.yneonled.com/blog/tiktok-room-neon-sign-ideas/) -> WALL_C lights-off/on open, neon strip under the mask, evening slots.
- Hashtag velocity and view-to-share ratios for #walldecor/#roomtransformation: UNAVAILABLE from free public pages today.

## MU API queue for TOMORROW (Mon Nov 23), one call at a time, check balance first (GET /account/balance), stop at $1.00
| # | call | input | purpose | cost |
|---|---|---|---|---|
| 1 | nano-banana-edit | real mask cutout + W_neon_on.png | relight the mask into the neon wall scene (real-print reference, shape must match; reject if swirls change) | $0.03 |
| 2 | nano-banana-edit | P_desk_pink.png | relight holder into the desk scene, softer edge/glow | $0.03 |
| 3 | nano-banana-edit | W_unbox.png | add hand-in-frame lifting the mask out of the tissue (AI-generated model) | $0.03 |
| 4 | hailuo i2v 768P/6s | output of #3 | unboxing lift-out motion clip | $0.30 |
| 5 | hailuo i2v 768P/6s | output of #2 | slow push-in on the holder while the AI gamer plays (static product check) | $0.30 |
| 6 | hailuo i2v 768P/6s | W_neon_off -> on still | lights-on reveal as true motion | $0.30 |
| | | | **total** | **$0.99** |
Each i2v result gets a frame-by-frame product check against the real photos; anything that redraws the logo plate or the swirl relief is discarded, not posted.
