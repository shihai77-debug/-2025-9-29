# EP20 CUT-12 Compression Execution Note

Use this note when generating CUT-12 prompts.

Source index official data:
- CUT-12 Duration: 6 seconds.
- Function: 檀缺 and 沈泊川 react silently.
- Dialogue: none.
- BGM: 弦乐维持，略带悬念感。
- SFX / environment: 安静，仅风声。
- Acting: 檀缺 glances at 黑七 with subtle recognition, then back to 陆沉舟. 沈泊川 stands tense, gaze on iron gate.

Important execution distinction:
- Official source duration is 6 seconds.
- If the user explicitly asks for / provides a compressed version, execute CUT-12 as a 3-4 second compressed reaction node rather than contradicting with the official 6-second source.
- The compressed version must preserve the same source content and continuity anchor:
  1. 檀缺's eyes lower briefly toward 黑七.
  2. 檀缺 immediately retrieves her gaze toward 陆沉舟.
  3. 沈泊川 stays frozen, watching only the iron gate.
  4. No dialogue. Wind sound only.

Recommended compressed runtime:
- Use 4 seconds for Jimeng / Seedance stability, since the platform may reject or weaken clips under 4 seconds.
- Do not expand it back to 6 seconds when the user asks for compression.

Do not add:
- New dialogue.
- Extra reaction beats.
- Door opening.
- Shen / Tan speaking.
- Black Qi speaking again.
- Electronic suspense music or heartbeat.
- Extra people or Han Zhixuan.

Final execution label:
- Source: KEEP in story.
- Prompt execution: COMPRESS to 4s when user requests compressed version.
