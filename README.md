# 🎌 YallAnime

> **Watch free anime online — Sub & Dub. No account needed.**

A single-file anime streaming site built for GitHub Pages, powered by the [Jikan API](https://jikan.moe/) and a custom Cloudflare Worker backend.

**Live Site:** [your-link-here](https://yallcode.github.io/yallanime)  
**Discord:** [Join the server](https://discord.gg/yUe8kE5fRF)  
**Developer:** [YallCode](https://YallCode.github.io/YallaYCode/)

---

## ✨ Features

- 🎬 **Stream anime** directly on the site — no redirects
- 🔤 **Sub & Dub** support with one click
- 📺 **Season switcher** — jump between seasons/sequels easily
- 📋 **Full episode list** with search — even 1000+ episode shows
- 🔍 **Live search** powered by MyAnimeList data
- 🏠 **Homepage** with trending, top airing, top rated, and movies
- 📄 **Anime info page** with stats, genres, studios
- 📱 **Fully responsive** — works on mobile, tablet, desktop
- ⚡ **Single HTML file** — easy to deploy anywhere

---

## 🚀 How It Works

```
User Browser
    │
    ├── Jikan API (jikan.moe)     → Anime metadata, images, ratings
    │
    └── Cloudflare Worker         → Fetches real stream URLs from GogoAnime
            │
            └── GogoAnime         → Actual video episodes
```

The site is 100% static (just `index.html`) and can be hosted for free on GitHub Pages. The Cloudflare Worker handles the backend scraping to avoid CORS issues.

---

## 📁 Files

| File | Description |
|------|-------------|
| `index.html` | The entire site — one file |
| `worker.js` | Cloudflare Worker script (deploy separately) |
| `icon.png` | Site favicon / logo |
| `README.md` | This file |

---

## 🛠️ Setup

### 1. Deploy the Cloudflare Worker

1. Go to [workers.cloudflare.com](https://workers.cloudflare.com) and sign in
2. Click **Create Worker**
3. Paste the contents of `worker.js` into the editor
4. Click **Deploy**
5. Copy your worker URL (e.g. `https://yallanime.yourname.workers.dev`)

### 2. Configure `index.html`

Open `index.html` and find this line near the top of the `<script>` tag:

```js
const WORKER = 'https://yallanime.yallcc-info.workers.dev';
```

Replace with your own worker URL if you're self-hosting.

### 3. Deploy to GitHub Pages

1. Push `index.html` and `icon.png` to a GitHub repo
2. Go to **Settings → Pages → Branch: main → Save**
3. Your site goes live at `https://yourusername.github.io/reponame/`

---

## 🔌 Worker API

Your Cloudflare Worker exposes these endpoints:

| Endpoint | Description |
|----------|-------------|
| `GET /` | Health check |
| `GET /search?q=naruto` | Search anime by name |
| `GET /slug?title=One+Piece` | Get GogoAnime slug + episode count |
| `GET /count?slug=one-piece` | Get real episode count from category page |
| `GET /embed?title=Naruto&ep=1` | Get embed URL for an episode |
| `GET /embed?title=Naruto&ep=1&dub=true` | Get dub embed URL |
| `GET /mirrors` | Test which GogoAnime mirrors are alive |
| `GET /debug?title=naruto` | Debug search results |

---

## 📬 Contact

- **Report an Issue / Request Anime:** [yallcc.info@gmail.com](mailto:yallcc.info@gmail.com)
- **Discord:** [discord.gg/yUe8kE5fRF](https://discord.gg/yUe8kE5fRF)
- **Developer Site:** [YallCode.github.io/YallaYCode](https://YallCode.github.io/YallaYCode/)

---

## ⚠️ Disclaimer

YallAnime does not host any video files. All video content is sourced from third-party providers via embedded players. This site is intended for educational and demonstration purposes. If you are a content owner and wish to have content removed, please contact us at [yallcc.info@gmail.com](mailto:yallcc.info@gmail.com).

---

<div align="center">
  <sub>Built with ❤️ by <a href="https://YallCode.github.io/YallaYCode/">YallCode</a></sub>
</div>
