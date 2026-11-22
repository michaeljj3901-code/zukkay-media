# Skills integration: AI batch 1122 (Skull controller holder)
Skills from Michael, Nov 22 2026, at /home/box/shared/skills/: create-viral-content v3.0.0 (SKILL.md + references/), trend-researcher.md, viral-video-analyst.md.
Precedence: **Zukkay lessons override the skills** (price + "link in bio" on screen from frame 1, no comment-keyword CTAs, FB on every post, no em dashes, live-verified prices).

## How each skill was used in this batch
| Skill | Used for | Output |
|---|---|---|
| trend-researcher | Public-web pass on the gaming-setup / controller-holder niche: momentum, competitors, gaps, risks. Unavailable metrics (hashtag WoW velocity, share ratios) are marked UNAVAILABLE, not estimated | skull/TREND_RESEARCH.md (top half) |
| viral-video-analyst | Breakdown of 1M+ view TikTok setup videos (Trendstalkr Nov 17 sample) plus Volume's Nov 21 format data, turned into 3 actionable rules | skull/TREND_RESEARCH.md (bottom half) |
| create-viral-content, step 3 hooks | 5 hooks per reel from its patterns (tribal split, before/after, specific item first), scored 0-3 for curiosity/specificity/emotion, best one picked | Hook tables in skull/captions/*.md |
| create-viral-content, step 5 AI tells | Captions scanned against the top-five list, the "Current-Model Tells (2026)" table and the TikTok/Reels tells, plus our em-dash rule (0 em dashes, 0 en dashes) | Check section in each caption doc |
| create-viral-content, step 6 five passes | Skeptic, Expert, Scroller, Competitor, Editor, logged per reel; stopped when a pass made no change | Refinement log in each caption doc |
| create-viral-content, step 8 disclosure | AI people labeled "AI-generated model" on screen and in captions. Platform toggles listed: TikTok "AI-generated content" (AIGC), Meta "AI info" label on IG and FB. NY synthetic-performer ad rule flagged for any paid use | Disclosure section in each caption doc |
| create-viral-content, platform rules | Hashtag caps found and verified: Instagram allows 5 per post (Help Center, Dec 2025), and TikTok has a reported in-app 5-tag cap (Aug 2025) with Creator Academy advising 2-3 | Primary captions use 5 tags. The brief's 30/15-20 tag sets are kept as an "extended tag bank" alternate only |

Conflicts resolved in Zukkay's favor:
- The skill's "closer should be a statement, not a request" vs. our save/share ask: we keep the save/share ask, since it's a Zukkay standing rule and not a comment-keyword CTA.
- The skill's "links cost reach" (LinkedIn/X data): it doesn't apply to IG/TT/FB, and "link in bio" stays on screen from frame 1.
- The skill's preference for 2-3 TikTok tags vs. the brief's "lead with #fyp #foryou #foryoupage #viral": the primary TT caption uses #fyp plus 1 niche tag plus the 3 required footer tags (5 total). The brief's 18-tag version is in the alternate bank for Chief/Michael to choose.

## Missing reference files
SKILL.md and README.md point to `references/viral-titles.md` and `references/viral-thumbnails.md`. **Neither file is in the repo.** The only related files present are `title-formulas.md` and `thumbnail-checklist.md`. Title scoring was done from the summary in SKILL.md ("Titles and thumbnails"). Ask Michael for the two files, or remove the references.

## Proposed engagement feedback loop (skill: references/feedback-loop.md, adapted to our data)
The skill stores posts in ~/viral-content-log/posts.json. Instead, we use **our existing table** /workspace/zukkay-content-pipeline/data/viral_metrics.csv (98 rows, Buffer `list_posts includeMetrics`, with columns such as hook_id, hook_type, views, avg_watch_s, saves, shares, link_clicks and sales already present).
1. **Log at publish:** when SoAMP/Buffer schedules a post, append a row with post_id, platform, product, hook_type (skill pattern: item-first / tribal / before-after / aesthetic), format (`ai_mix` vs `real`), and an `ai_assets` field with the model names (new column), plus caption_head and time_slot.
2. **Reads:** The Coder's metric reads (IG, FB and TT views, watch time, saves, shares) at <24h, 7d and 30d, written as `snapshot` rows (the 24h/7d/30d checkpoints match the skill's schedule). Buffer per-post metrics fill the same columns. Sales and link clicks come from sales_ledger.csv / Stripe and are matched by product + date.
3. **Score:** per post, compute the skill's composite (0.4 normalized views + 0.3 engagement rate + 0.2 velocity + 0.1 longevity), normalized against **our own** account median per platform, not the skill's absolute tiers (our 5,398-view Skull reel is "viral" for us).
4. **Learn weekly** (or every 10 posts, whichever comes first, per the skill): top 20% vs. bottom 20% by hook_type, format (AI mix vs. real), product, slot and platform. Write the findings to a lessons file Chief reads, so the A/B of Reel 1 (proven hook) vs. Reel 2 (in-use AI opener) gets a real answer.
5. **Guardrails:** no fabricated metrics (empty means not read yet), the skill's "never promise detector evasion", and the MUAPI cost per post is logged alongside so cost per view is visible.

## reels-af (pattern library only: NOT run, no OpenRouter or other LLM/TTS API calls)
Source: /home/box/shared/skills/reels-af/ (read src/reel_af/models.py, agents/critic.py, agents/judge.py, render/subtitles.py, render/stitch.py).
| Technique | Used? | How |
|---|---|---|
| Hook -> Mechanism -> Payoff script (models.ScriptDraft: 2-4 mechanism lines, payoff echoes a hook keyword for the loop) | Yes | Reel 1: "Park your controller here." -> Off the couch / Onto the skull / Printed to order / Set it down -> "PARKED." Reel 2: "Your controller needs a parking spot." -> Set it down / Lights on / No more couch cushions / Printed to order -> "SPOT TAKEN." |
| Word-burst karaoke subtitles (render/subtitles.py: one word alone on screen, big bold outlined, via a libass .ass file) | Yes | skull/build/reel1.ass and reel2.ass: Anton 170 px, 11 px black outline, a 115%->100% pop per word, white/yellow/red accents, top-third placement so it never covers the product or the frame-1 price bar (reels-af puts it at 74% height, which would collide with our price bar). There is no TTS, so words are timed to the visual cuts, not to audio. |
| Critic + judge pass (agents/critic.py scoring + agents/judge.py priority order) | Yes, by hand | 3 scripts per reel scored on hook strength, specificity, loop-back, trope avoidance, flow, stake, plus Zukkay retention rules. The winner is kept. See skull/SCRIPTS_JUDGE.md |
| Single-pass ffmpeg stitch (render/stitch.py: concat filter + libass burn + audio mux in one call) | Yes, it was cleaner | v1 used 3 encodes (concat demuxer, then overlays + audio, then a loudness fix). v2 uses 1 final encode: concat filter + PNG overlays + subtitles (ASS) + audio with a pre-measured gain in a single ffmpeg call (skull/build_v2.py). The result hits -14.1 / -14.0 LUFS directly, with no loudness re-encode and fewer generation losses. |
| Not used | | Article hunters/narrator/TTS, Veo clip generation, OpenRouter calls, and the Docker app. None of these apply, and the brief forbids running it. |
