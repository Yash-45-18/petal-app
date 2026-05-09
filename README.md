# 🐾 Petal — AI Virtual Pet App

Adopt an AI-powered pet with a real personality. Feed it, play with it, chat with it, and watch it grow. Invite a friend to co-parent together!

## 🚀 Deploy to Vercel (5 minutes)

### Step 1 — Push to GitHub

```bash
git init
git add .
git commit -m "Initial commit — Petal AI pet app"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/petal-app.git
git push -u origin main
```

### Step 2 — Deploy on Vercel

1. Go to [vercel.com](https://vercel.com) and sign in with GitHub
2. Click **"Add New Project"**
3. Import your `petal-app` repo
4. Click **Deploy** — Vercel auto-detects the config

### Step 3 — Add your API key (critical!)

1. In Vercel dashboard → your project → **Settings → Environment Variables**
2. Add a new variable:
   - **Name:** `ANTHROPIC_API_KEY`
   - **Value:** `sk-ant-your-key-here`
   - **Environment:** Production, Preview, Development
3. Click **Save**
4. Go to **Deployments** → click **Redeploy** (so the env var takes effect)

Your app is now live at `https://petal-app.vercel.app` 🎉

---

## 📁 Project Structure

```
petal-app/
├── index.html        # Full app UI + frontend logic
├── api/
│   └── chat.js       # Serverless proxy (keeps API key safe)
├── vercel.json       # Vercel routing config
├── package.json      # Node config
└── .gitignore        # Excludes .env and node_modules
```

## 🔐 How the proxy works

```
Browser → POST /api/chat → Vercel Function → Anthropic API
                            (API key lives here, never exposed)
```

The frontend calls `/api/chat` (your own server), never Anthropic directly.
Your API key is stored as an environment variable in Vercel — never in your code.

## 🔑 Get an Anthropic API Key

1. Go to [console.anthropic.com](https://console.anthropic.com)
2. Sign up / log in
3. Go to **API Keys** → **Create Key**
4. Copy the key and paste it into Vercel's environment variables

## ✨ Features

- 🥚 Pet creation — choose species, name, and starting personality
- 🎮 Daily care — feed, play, talk, rest with stat tracking
- 🤖 AI personality engine — mood-aware responses via Claude
- 📔 Pet journal — auto-logs every milestone and interaction
- 🌱 Growth stages — Baby → Teen → Adult as you interact more
- 👫 Co-parenting — shareable invite link for a friend

## 🛠 Local Development

```bash
npm install -g vercel
vercel dev
```

Then open `http://localhost:3000`. Set your API key in a `.env.local` file:


