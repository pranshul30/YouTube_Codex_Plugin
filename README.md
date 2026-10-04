# YouTube Growth Copilot for ChatGPT & Codex

**Turn “I have a video idea” into “this is ready to record.”**

YouTube Growth Copilot is an OpenAI-compatible creator toolkit for hooks, scripts, titles, thumbnails, Shorts, editing decisions, retention analysis, SEO, chapters, planning, comments, viral research, and channel audits.

It is a ChatGPT/Codex port of Jake Schincariol's MIT-licensed **youtube-agent-skill**, adapted to OpenAI's current plugin + skill format.

## Highlights

- **Score hooks instead of guessing** with a real Python heuristic and 21 hook formulas.
- **Package title + thumbnail together** so they do not repeat or weaken each other.
- **Find attention leaks** from retention exports and transcript timing.
- **Turn long-form into Shorts** with rewritten short-form openings.
- **Keep the human in control:** nothing auto-publishes.

## Included skills

| Skill | What it does |
| --- | --- |
| `yt-script` | Five hooks, scored, then a spoken script with on-screen beats. |
| `yt-package` | Lints title + thumbnail for clarity, truncation, and duplication. |
| `yt-edit` | Turns a transcript into an edit decision list. |
| `yt-comment` | Triages comments and drafts replies in your voice. |
| `yt-plan` | Builds a realistic weekly content plan. |
| `yt-viral` | Ranks niche videos by performance versus channel baseline. |
| `yt-retention` | Finds hook leaks, cliffs, and slides in retention data. |
| `yt-shorts` | Finds Shorts already hiding inside long-form content. |
| `yt-seo` | Drafts search-focused descriptions and query targets. |
| `yt-chapters` | Generates and validates YouTube chapters. |
| `yt-audit` | Audits a channel and ends with one prioritized fix. |

## Install in Codex

```bash
codex plugin marketplace add pranshul30/YouTube_Codex_Plugin
codex plugin marketplace list
```

Then install **YouTube Growth Copilot** from that marketplace in a supported Codex/ChatGPT desktop plugin surface.

## Use

Ask explicitly:

```text
Use yt-script to write a video about building an AI WhatsApp campaign platform.
```

Or just describe the job:

```text
Give me five YouTube hooks for this idea, score them, then write the winning script.
```

## Creator voice

Copy `templates/voice.md` to `.youtube/voice.md` in the project you use with Codex.

Local Codex users can also keep a profile at `~/.codex/youtube/voice.md`.

If no profile is available, provide three representative scripts/transcripts and let the skill infer a working voice for the session.

## Included Python tools

```bash
python3 skills/yt-script/hookscore.py --hook "one line"
python3 skills/yt-package/title.py --title "..." --thumb "..."
python3 skills/yt-edit/deadair.py transcript.srt
python3 skills/yt-chapters/chapters.py transcript.srt
python3 skills/yt-retention/retention.py retention.csv
python3 skills/yt-viral/swipe.py collected.json --min 2.0
```

No third-party Python packages are required.

## Limitations

- Hook scores are heuristics, not view predictions.
- The plugin does not publish to YouTube.
- It must not invent analytics, results, numbers, or sources.
- Some workflows require your transcript, CSV export, screenshots, or channel data.

## Attribution

Original project: **The YouTube agent skill** by Jake Schincariol.
Source: https://github.com/Jakeschincariol/youtube-agent-skill

The original MIT license and copyright notice are retained.

## License

MIT. See `LICENSE`.
