# Yashwanth Anandan — Personal Profile & Technical Blog

A modern, minimalist, high-performance portfolio and blog built with **[Astro](https://astro.build/)**, **Tailwind CSS**, and **Markdown/MDX Content Collections**.

- **Live URL**: [https://yashwanth.tech](https://yashwanth.tech)
- **Local Dev**: `http://localhost:4321`

---

## 🚀 Running Locally

```bash
# 1. Install Dependencies
npm install

# 2. Start Local Development Server
npm run dev
```

Open **`http://localhost:4321`** in your browser. Live reloading is automatically enabled.

To test the production build locally:
```bash
npm run build
npm run preview
```

---

## 🌐 Connecting `yashwanth.tech` (Domain & GitHub Pages Setup)

To make `https://yashwanth.tech` serve this website, follow these simple steps:

### Step 1: Push Code to GitHub
Create a GitHub repository (e.g. `yashanandan/portfolio` or `yashanandan/yashanandan.github.io`):
```bash
git init
git add .
git commit -m "feat: initial profile and blog for yashwanth.tech"
git branch -M main
git remote add origin https://github.com/<your-username>/<your-repo-name>.git
git push -u origin main
```

### Step 2: Enable GitHub Pages with Actions
1. Go to your GitHub repository -> **Settings** -> **Pages**.
2. Under **Build and deployment** -> **Source**, select **GitHub Actions**.
   *(The workflow at `.github/workflows/deploy.yml` will automatically build and deploy whenever you push to `main`)*.
3. Under **Custom domain**:
   - Enter: `yashwanth.tech`
   - Click **Save**.
   - Check the box for **Enforce HTTPS** (GitHub will provision a free SSL certificate).

*(Note: We already created `public/CNAME` containing `yashwanth.tech`, so your custom domain setting will never be overwritten on subsequent builds).*

### Step 3: Configure DNS Records in Your Domain Registrar
Log into wherever you purchased `yashwanth.tech` (e.g., Namecheap, Cloudflare, GoDaddy, Google Domains / Squarespace, Porkbun) and go to your **DNS Management / Advanced DNS** settings.

Add the following **4 A records** (for the apex domain `@`):

| Type | Name / Host | Target / IP Address | TTL |
| :--- | :--- | :--- | :--- |
| **A** | `@` (or leave blank) | `185.199.108.153` | Automatic / 300 |
| **A** | `@` (or leave blank) | `185.199.109.153` | Automatic / 300 |
| **A** | `@` (or leave blank) | `185.199.110.153` | Automatic / 300 |
| **A** | `@` (or leave blank) | `185.199.111.153` | Automatic / 300 |

*(Optional but recommended)* For `www.yashwanth.tech` redirect to root:
| Type | Name / Host | Target / Value |
| :--- | :--- | :--- |
| **CNAME** | `www` | `<your-github-username>.github.io.` |

Once DNS propagates (usually 5–15 minutes), visiting **`https://yashwanth.tech`** will serve your profile and blog with automatic HTTPS.

---

## ✍️ Writing New Blog Posts

All articles live in `src/content/blog/` as clean Markdown (`.md`) files.

Create a new file, e.g., `src/content/blog/my-next-article.md`:

```markdown
---
title: "Article Title Here"
description: "A short 1-2 sentence overview for preview cards & SEO."
pubDate: 2026-11-21
tags: ["Distributed Systems", "Architecture", "Observability"]
readTime: "6 min read"
draft: false
---

Your markdown content here...
```

Push your changes to GitHub, and the workflow deploys your post automatically in under 60 seconds.
