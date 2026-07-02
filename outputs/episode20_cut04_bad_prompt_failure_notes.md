# EP20 CUT-04 Bad Prompt Failure Notes

Use this note when repairing CUT-04 prompts.

Bad prompt patterns that caused wrong video:
- Generic labels like young man, young woman, black fox instead of exact names Lu Chenzhou, Hei Qi, Tan Que.
- Wrong action: Lu reads a newspaper. In source, Lu already holds documents from CUT-03 and remains seated.
- Wrong action: Tan Que slowly walks in. In source, Tan Que is already present and only shifts gaze.
- Wrong concept words: symbolic, surreal, post-apocalyptic meeting, wasteland, mystical fox. These change genre and make background/story wrong.
- Wrong focus: black fox looking at lens. In source, Hei Qi only has a slight ear movement.
- Wrong duration split: 4 seconds. In source, CUT-04 is 8 seconds.
- Wrong camera/background emphasis: deep focus, wide wasteland, 8k. This makes background too dominant and weakens character continuity.

Correct source logic:
- CUT-04 duration is 8 seconds.
- 0-3s: Hei Qi ear moves slightly, only action.
- 3-8s: Tan Que looks from Hei Qi to Lu Chenzhou.
- No dialogue.
- Lu already has documents and remains seated.
- No document handoff in CUT-04.

Prompt repair rule:
- Use exact character names and reference tags.
- Avoid symbolic interpretation.
- Avoid apocalypse/wasteland genre words.
- Keep action minimal and faithful to source index.
- Storyboard board is only for blocking and reaction order, not final face, clothing, or text.
