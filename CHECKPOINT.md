# Lectio — Session Checkpoint

## Project overview
- **Landing page:** `index.html` hosted on GitHub Pages → https://yogevshakedmusic.github.io/lectio/
- **Notebook:** `lectio.ipynb` opens in Google Colab via the landing page CTA button
- **Repo:** https://github.com/YogevShakedMusic/lectio (user: YogevShakedMusic)
- **Donations:** Ko-fi → https://ko-fi.com/yogevshaked

---

## Current state of index.html (landing page)

### Sections (top to bottom)
1. **Nav** — logo, "How it works", "FAQ", "Feedback" links + Ko-fi donate button
2. **Hero** — headline, subtext, "Start transcribing" CTA button (links to Colab)
3. **How it works** (#how) — 4-step card grid
4. **Why Lectio** (dark) — 6 feature cells
5. **Compatibility** — video/audio format pills + language grid
6. **Donate** (#donate) — Ko-fi link
7. **Feedback** (#feedback) — two cards: GitHub Issues (bug/idea) + Ko-fi (thanks)
8. **FAQ** (#faq) — 6 questions
9. **CTA bottom** — repeat "Start transcribing" button
10. **Footer** — GitHub link + Donate link

### What was removed
- "What it looks like" section (Colab UI mockup) — removed, was between Why Lectio and Compatibility

---

## Current state of lectio.ipynb (Colab notebook)

### Cells
- **cell-0 (markdown):** Header with logo + "How to start" instructions for both desktop and phone
- **cell-1 (code, hidden):** Setup — installs ffmpeg + faster-whisper, checks for GPU
- **cell-2 (code, hidden):** Configure & Transcribe — language dropdown, format toggle (TXT/SRT/Both), file upload, transcription, progress bar, stats, preview
- **cell-3 (code, hidden):** Download — success card, downloads file(s), tips, Ko-fi link

### Key features
- All code cells hidden (`cellView: form`) — users see zero code
- **Language selector:** dropdown, 15 languages + auto-detect
- **Output format:** `ToggleButtons` widget — TXT, SRT (with Whisper timestamps), or Both
- **SRT generation:** proper `HH:MM:SS,mmm --> HH:MM:SS,mmm` format from Whisper segments
- **Progress bar:** live updates every 2%, shows % complete + seconds remaining
- **Stats card:** word count, character count, detected language
- **Mobile instructions:** ☰ → Runtime → Run all

---

## Things that could still be improved (ideas)
- Landing page mobile responsiveness (nav, cards, hero layout on small screens)
- Add a real contact form or email for feedback instead of just GitHub Issues
- Consider adding a demo video or GIF to the landing page
- README.md still has placeholder `YOUR_GITHUB` in the Colab badge link (line 5) and donation link (line 93) — never touched, may want to fix
- The notebook's language dropdown width (`380px`) may overflow on mobile Colab
