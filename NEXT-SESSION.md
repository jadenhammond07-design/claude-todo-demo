# Continue the Stick3D video factory in a new session

1. Unzip the newest `Stick3D-Pack-v*.zip` from this repo/branch (`claude/video-generation-setup-gy32vu`) and follow its MASTER-PROMPT.md "FIRST MESSAGE BEHAVIOUR" (run `00-setup/setup.sh`, read all rules incl. `rules/VIRAL-PLAYBOOK.md`).
2. Free voice: `python3 -m venv /root/.tts-venv && /root/.tts-venv/bin/pip install kokoro-onnx soundfile`, then download `kokoro-v1.0.onnx` and `voices-v1.0.bin` (github.com/thewh1teagle/kokoro-onnx releases, model-files-v1.0) into `/root/.tts-models`. Voice = am_adam, speed 1.2 (tools/tts.py defaults).
3. Output: HD 1080x1920 (remotion.config.ts scale 1.5), on-screen hook + COMMENT BELOW end question on every video, caption + hashtags + post time with each delivery, target 30-40 s.
4. vidIQ connector is connected: use it for every video (see VIRAL-PLAYBOOK.md "vidIQ").
5. After each video: send the HD mp4, rebuild the pack zip (exclude node_modules, chunks*, 99-exports, 02-videos/*/mix.wav), commit + push to this branch.

## Long-form YouTube (16:9, 2D cartoon style) — added later
- Engine: `engine/src/long/` in the pack (kit2d.ts props/backgrounds, *Beats.ts timed scenes, Wealth.tsx/Biz7.tsx compositions; register 1920x1080 in Root). Render with `--scale=1` (fast, ~7 min per 2.5k frames).
- Voice per chapter: `TTS_GAP=0.32 tools/tts.py chapter.txt out.mp3 am_adam 1.0`, align each with `tools/voice/align.py`, stitch with 3 s chapter cards (see 02-videos/wealth/timeline.json build).
- Deliver: mp4 (compress with crf 20 if >100 MB for GitHub), 1280x720 thumbnail, YOUTUBE.txt (3 titles, description with chapter timestamps, tags), .srt subtitles from word timings.
- ~150 words = 1 minute; tell the user if the script is shorter than the length they want.
