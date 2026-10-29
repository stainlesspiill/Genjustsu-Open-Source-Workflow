<p align="center">
  <a href="https://tein.ai?utm_source=genjutsu&utm_medium=readme&utm_campaign=banner"><img src="docs/branding/tein-ai-banner.svg" width="960" alt="TEIN AI — Open-source AI workflows. Click to join the waitlist." /></a>
</p>
<p align="center">
  <a href="https://tein.ai?utm_source=genjutsu&utm_medium=readme&utm_campaign=waitlist"><strong>Join TEIN AI →</strong></a> · <a href="https://app.enhancor.ai/api-dashboard?utm_source=genjutsu&utm_medium=readme&utm_campaign=api">Get Seedance API</a> · <a href="#-try-it-in-2-minutes">2-min demo</a> · <a href="LICENSE">MIT</a>
</p>

# Genjutsu — Replace Any Actor in Your Video

**Your scene. New cast. Your audio, untouched.**

Upload your clip → approve the mask → add a face → get draft → 1080p. Open-source (MIT), no GPU, runs on your machine (127.0.0.1). Depth + SAM 3 + Enhancor Seedance 2.5. Byte-for-byte original audio restoration.

> **Not face-swap.** Full-body replacement — hair, hands, clothes, shoes — via colored depth + SAM masks. Original background, camera, light & music stay perfect.

<p align="center">
  <a href="examples/advanced-black-nodes-v8-audio.mp4"><img src="examples/previews/workflow.gif" width="28%" alt="Workflow — depth to final, click for video with audio" /></a>
  <a href="examples/1006%20%281%29.mp4"><img src="examples/previews/example-1.gif" width="34%" alt="Example 1 — café dialog, click for video with audio" /></a>
  <a href="examples/1006%20%281%29%283%29.mp4"><img src="examples/previews/example-2.gif" width="34%" alt="Example 2 — two-person cast, click for video with audio" /></a>
</p>
<p align="center"><em>Silent previews — click any for full video with audio.</em></p>

---

## Is this free?

**Yes — the workflow is MIT free.** Your code runs locally. You pay only the hosted APIs you already use, directly:

| What | Provider | ~Cost for 10s | You pay |
|---|---|---|---|
| Demucs + Depth + SAM | Replicate | $0.25–0.40 | Replicate (your token) |
| Seedance draft | Enhancor | $0.90–1.50 | Enhancor (your key) |
| Seedance 1080p | Enhancor | ~2.8× draft | Enhancor (same key) |
| Hosting `tmpfiles→catbox` | free | $0 | — |

**No subscription, no markup.** Enhancor is currently the lowest public Seedance price with unrestricted use/human-face support. We disclose if we ever earn a referral — you still pay list. Draft is gated behind your mask approval, so you never pay for a bad input.

---

## ✨ What’s inside

- **3 pillars:** Full-body replacement · Original audio restored · Draft-first (approve before 1080p)
- **MIT** code + docs — bring your own `ENHANCOR_API_KEY` + `REPLICATE_API_TOKEN`
- No local GPU/model weights for default mode; local mux + Rubber Band pitch
- Hosted optional: `HF_TOKEN` for Hugging Face depth alternative
- Persistent jobs: `workflow.py status/resume`, collector resumes on restart

**Tech:** Python 3.12+, FastAPI, PyAV/NumPy/OpenCV/SciPy, Demucs (Replicate), Rubber Band CLI (+3 semitones, timing preserved), `lucataco/depth-anything-video` (colors preserved), `lucataco/sam3-video`, Enhancor Seedance Edit/Omni, Cloudflare Quick Tunnel for webhook.

---

## 🎬 Watch the workflow and examples

### Workflow walkthrough

[![Workflow](examples/previews/workflow.gif)](examples/advanced-black-nodes-v8-audio.mp4)

[Watch full workflow with audio](examples/advanced-black-nodes-v8-audio.mp4)

### Example 1 — café dialog

[![Example 1](examples/previews/example-1.gif)](examples/1006%20%281%29.mp4)

*One subject replaced, hands + coffee steam kept.*

[Watch with audio](examples/1006%20%281%29.mp4)

### Example 2 — double cast

[![Example 2](examples/previews/example-2.gif)](examples/1006%20%281%29%283%29.mp4)

*Two references → two roles, music intact.*

[Watch with audio](examples/1006%20%281%29%283%29.mp4)

Previews = first 6s, silent. See [all example files](examples/README.md). Examples optional; processing them bills your API accounts.

---

## 🚀 Get access

- **[Join TEIN.ai](https://tein.ai?utm_source=genjutsu&utm_medium=readme&utm_campaign=waitlist)** — cheapest APIs, open workflows, template library & Batch API alerts.
- **[Get Seedance API at Enhancor.ai](https://enhancor.ai?utm_source=genjutsu&utm_medium=readme&utm_campaign=enhancor)** — `pass_faces: true`, draft previews, approved 1080p. Dashboard: [app.enhancor.ai/api-dashboard](https://app.enhancor.ai/api-dashboard).

---

## 🤖 Easiest setup — let your coding agent do it

Extract ZIP, open folder in Codex (or any agent with terminal), paste:

> Set up this TEIN Genjutsu project for me. Read `docs/SETUP-AGENT.md` end to end. Detect OS, install Python/Rubber Band/cloudflared, create `.venv`, install deps, install Python 3.12 + `bash setup-face-mesh.sh` for mesh modes, create `.env` without overwriting. Open `.env` for my keys. Run tests, launch app + callback tunnel, run readiness check on free port, verify UI + companions, give me URL. Don't submit paid generations. If keys missing, tell me generation is waiting.

Launcher creates a callback-only Quick Tunnel when `ENHANCOR_WEBHOOK_URL` is blank (keep it running). Native Windows → WSL2; macOS/Linux scripts included.

## 🛠️ Manual setup

1. **Prereqs — Python 3.12+ (dev on 3.14.6) + Rubber Band:**
   - macOS: `brew install rubberband cloudflared`
   - Ubuntu/Debian/WSL: `sudo apt install rubberband-cli python3-venv` + [cloudflared](https://developers.cloudflare.com/cloudflare-one/connections/connect-networks/downloads/)
2. **Install:** `bash setup.sh` → creates `.venv`, installs `requirements.txt`, creates blank `.env`. For all 3 modes: install Python 3.12 + `bash setup-face-mesh.sh`, then `.venv/bin/python doctor.py --mesh` (macOS: `brew install python@3.12`).
3. **Keys:** fill `.env` with your own `ENHANCOR_API_KEY` (from Enhancor) and `REPLICATE_API_TOKEN` (from Replicate). Fund accounts. `HF_TOKEN` optional.
4. **Run:** `./start.command` (or `bash start.command`) → open **http://127.0.0.1:8770** (use `PORT=8771 bash start.command` if busy). Check `.venv/bin/python doctor.py --require-keys`. Keep app + tunnel running — Enhancor requires webhook.
5. Upload MP4/MOV → prepare → review **entire** mask/mesh + prepared video → approve that exact artifact → add refs → review prompt → draft.
6. Like draft → **Approve & generate 1080p**. Draft + HD kept separate; both use source audio.

No weights/GPU needed for hosted mode. Four user-selected demo videos in `examples/`; TEIN companion art bundled (excluded from MIT).

---

## 🔮 What happens (pipeline)

1. Save source unchanged; extract audio & separate vocals/music with Demucs (Replicate).
2. Pitch isolated vocals **+3 semitones**, duration preserved via Rubber Band.
3. Normalize working video to 24 fps, ≤960px; colored depth via `lucataco/depth-anything-video` (colors preserved).
4. SAM 3 raw PNG masks on depth. Agent can retry on original RGB if depth loses detail.
5. Composite depth subject over original background. **Mandatory full-clip mask review** gates every generation (hash-bound approval).
6. Embed pitched vocals in composite MP4. Send this video — no standalone audio — with refs.
7. Enhancor Seedance **Edit** (image refs) or **Omni / multi_reference** (video identity ref). Draft first.
8. Poll, download, discard AI audio, copy complete original soundtrack into final MP4.
9. On explicit HD approval, complete accepted draft at 1080p, restore soundtrack again.

---

## ⚡ Fast alternative — face mesh

Choose **Fast · Face mesh** in UI or `workflow.py prepare VIDEO --mode face_mesh`. Install once: `bash setup-face-mesh.sh` (Python 3.12, isolated `.venv-face`, auto-downloads Google Landmarker).

Keeps original video, tracks facial landmarks, draws mesh, isolates + pitches + embeds vocals. **No depth/SAM calls.** Single centered speaker; inspect all frames for tracking gaps. Same refs, draft→HD, audio restoration. Explain in prompt that mesh lines are motion guidance and must disappear.

### Combined depth + face mesh

**Advanced + Face mesh** (`--mode depth_mesh`): depth/SAM composite + mesh overlay; landmarks in `face-landmarks.json`. Review BOTH before approval.

---

## 🧭 Agent operations

Open folder in agent, ask to follow `AGENTS.md` + `.agents/skills/tein-video-workflow/SKILL.md`. No vendor lock-in — agent must inspect video/files, run Python, access net. No silent service. Example:

> “Use Genjutsu for my clip + refs. Prepare, inspect entire mask, repair if needed, show prompt, submit authorized draft, retrieve preview. Wait for my HD approval.”

See [AGENT-OPERATIONS.md](docs/AGENT-OPERATIONS.md), [ENHANCOR-API.md](docs/ENHANCOR-API.md), [MODELS.md](docs/MODELS.md), [MEDIA-HOSTING.md](docs/MEDIA-HOSTING.md), [TROUBLESHOOTING.md](docs/TROUBLESHOOTING.md).

---

## 🔁 Recovery and checks

```bash
.venv/bin/python doctor.py --require-keys
.venv/bin/python test_composite.py
.venv/bin/python -m unittest discover -s tests
.venv/bin/python workflow.py status LOCAL_JOB_ID
.venv/bin/python workflow.py resume LOCAL_JOB_ID
.venv/bin/python workflow.py resume LOCAL_JOB_ID --hd
```

Server resumes saved Seedance/HD **collection** on restart — never re-submits paid jobs. Interrupted prep: inspect saved prediction metadata; don't blindly re-bill. One server/collector per job. Local single-user app — add auth + queue before public hosting.

---

## ✅ Tested release

Clean install on macOS ARM64, Python 3.14.6 — 13 tests passed + live draft→1080p run & browser download; test fixed Tmpfiles URL + webhook setup; source audio verified byte-for-byte. See [VALIDATION.md](docs/VALIDATION.md). Other OS / Catbox route not live-tested yet.

## 📦 Sharing

Share clean ZIP, or remove `.env`, `.venv`, `runs`, logs before repackaging. Runs contain private media/URLs. Dependencies/services retain their licenses. See [THIRD-PARTY.md](THIRD-PARTY.md).

---

## Before publishing on GitHub

Use clean project folder (not installation with jobs/creds). `.gitignore` excludes secrets/envs/jobs/logs but can't scrub history. Keep `.env.example` blank; never commit `.env`, webhook URLs, provider responses, runs. No history in ZIP. Code/docs MIT; example videos + TEIN art excluded. Designed for localhost, not unauthenticated public deploy.

## License

Code & docs: [MIT](LICENSE), © 2026 Sirio Berati. TEIN names/logos/artwork & example media excluded; respective owners retain rights. Third parties retain their licenses — see [THIRD-PARTY.md](THIRD-PARTY.md).

---

## Tech stack

| Layer | Technology |
|---|---|
| App | Python 3.12+, FastAPI, Uvicorn; HTML/CSS/JS UI |
| Video/audio | PyAV, NumPy, Pillow, OpenCV, SciPy; local encoding/composite/audio restore |
| Vocal isolation | Hosted Demucs / htdemucs via Replicate |
| Pitch | Rubber Band CLI — +3 semitones, duration preserved |
| Depth | `lucataco/depth-anything-video` (alt: HF Video Depth Anything, `chenxwh/depth-any-video`) |
| Segmentation | `lucataco/sam3-video` — raw masks + mandatory review |
| Face mesh | Google MediaPipe Face Landmarker, isolated Py3.12 worker |
| Generation | Enhancor Seedance — Edit (images), Omni (video refs) — draft → approved 1080p |
| Media hosting | Tmpfiles primary, Catbox fallback (direct-link checked) |
| Completion | Persisted jobs + polling; Cloudflare Quick Tunnel callback |
| Agent | AGENTS.md, setup runbook, skill + CLI |

---

## Hosting and failure recovery

Default `.env.example`: `MEDIA_HOST=tmpfiles`, `MEDIA_HOST_FALLBACKS=catbox` (two attempts each, short delay). Fell back host is reported. **Both expose public URLs; Catbox persistent.** Set `FALLBACKS=` to disable, or Catbox as primary. `CATBOX_USERHASH` optional. Uploader checks for HTTP errors/empty/HTML pages — can't guarantee later provider access or codec compat. Tmpfiles expires: re-upload for regeneration. Failed upload never triggers generation. Paid gens not auto-retried: inspect saved request/status to avoid double-charge. Polling = source of truth. See [MEDIA-HOSTING.md](docs/MEDIA-HOSTING.md).
