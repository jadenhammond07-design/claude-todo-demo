# Continue the Stick3D video factory in a new session

1. Unzip the newest `Stick3D-Pack-v*.zip` from this repo/branch (`claude/video-generation-setup-gy32vu`) and follow its MASTER-PROMPT.md "FIRST MESSAGE BEHAVIOUR" (run `00-setup/setup.sh`, read all rules incl. `rules/VIRAL-PLAYBOOK.md`).
2. Free voice: `python3 -m venv /root/.tts-venv && /root/.tts-venv/bin/pip install kokoro-onnx soundfile`, then download `kokoro-v1.0.onnx` and `voices-v1.0.bin` (github.com/thewh1teagle/kokoro-onnx releases, model-files-v1.0) into `/root/.tts-models`. Voice = am_adam, speed 1.2 (tools/tts.py defaults).
3. Output: HD 1080x1920 (remotion.config.ts scale 1.5), on-screen hook + COMMENT BELOW end question on every video, caption + hashtags + post time with each delivery, target 30-40 s.
4. vidIQ connector is connected: use it for every video (see VIRAL-PLAYBOOK.md "vidIQ").
5. After each video: send the HD mp4, rebuild the pack zip (exclude node_modules, chunks*, 99-exports, 02-videos/*/mix.wav), commit + push to this branch.
