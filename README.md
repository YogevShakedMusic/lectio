# Lectio — Free Lecture Transcription for Students

> Turn any Zoom recording or audio file into text — free, private, no account needed.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/YOUR_GITHUB/lectio/blob/main/lectio.ipynb)

---

## What is this?

Lectio is a free tool that transcribes lecture recordings into text using OpenAI's Whisper AI model. It runs entirely on Google's free GPU infrastructure via Google Colab — meaning it costs you nothing to run and nothing to offer to others.

Built by a student who needed to feed lecture transcripts to AI for homework help. Then shared because every student with recorded lectures can use it.

## How it works

1. User visits your website (free GitHub Pages / Vercel / Netlify hosting)
2. Clicks "Start transcribing" → opens this Colab notebook
3. Hits "Run All" in Colab
4. Uploads their lecture file (any video or audio format)
5. Waits ~3-6 minutes
6. Transcript downloads automatically as a .txt file

**The user never sees a single line of code.**

## Tech stack

- **Transcription**: [faster-whisper](https://github.com/SYSTRAN/faster-whisper) with `large-v2` model
- **Audio compression** (optional, for large files): ffmpeg with Opus codec
- **Website**: Plain HTML/CSS, hosted on GitHub Pages for free
- **Compute**: Google Colab free tier (user's own Google account)
- **Your cost**: $0

## Setup — deploy your own copy in 10 minutes

### 1. Fork this repo
Click Fork at the top right of this GitHub page.

### 2. Update your username in the files
Replace `YOUR_GITHUB` and `YOUR_USERNAME` in:
- `index.html` (3 places — Colab link, GitHub link, Buy Me a Coffee link)
- `lectio.ipynb` (1 place — Buy Me a Coffee link)

### 3. Enable GitHub Pages
- Go to your repo → Settings → Pages
- Source: Deploy from branch → main → / (root)
- Click Save
- Your site will be live at `https://YOUR_GITHUB.github.io/lectio`

### 4. Set up donations (optional)
- Create a free account at [buymeacoffee.com](https://buymeacoffee.com)
- Replace `YOUR_USERNAME` in both files with your Buy Me a Coffee username

### 5. Update the Colab link
The Colab button links to:
```
https://colab.research.google.com/github/YOUR_GITHUB/lectio/blob/main/lectio.ipynb
```
Replace `YOUR_GITHUB` with your actual GitHub username.

That's it. Your site is live and costs you nothing.

## Accuracy

Whisper `large-v2` is one of the most accurate open-source transcription models available. It supports 90+ languages including Hebrew, Arabic, Russian, and other languages underserved by commercial tools.

For best results:
- Use the original recording, not a screen-recorded version
- Audio compression with ffmpeg before upload helps with very large files (see below)

## Optional: Compress files before uploading

If your recording is very large (>500MB), you can compress it first with ffmpeg. This makes upload faster and doesn't affect transcription quality at all.

**Convert video to compressed audio:**
```bash
ffmpeg -i lesson.mp4 -vn -map_metadata -1 -ac 1 -c:a libopus -b:a 12k -application voip lesson.ogg
```

**Convert WAV to compressed audio:**
```bash
ffmpeg -i lecture.wav -vn -map_metadata -1 -ac 1 -c:a libopus -b:a 12k -application voip lecture.ogg
```

This reduces a 1GB video to ~10-15MB while keeping the voice perfectly clear for transcription.

## License

MIT — free to use, modify, and share. If you build something with it, a mention would be appreciated but isn't required.

## Donate

If Lectio saved you hours of re-watching lectures, consider [buying me a coffee](https://buymeacoffee.com/YOUR_USERNAME). It helps keep the site running and motivates further improvements.
