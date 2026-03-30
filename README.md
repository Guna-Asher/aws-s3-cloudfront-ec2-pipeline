# 🚀 CI/CD Practice Project - Automated S3 Deployment Demo

[![GitHub Workflow Status](https://github.com/badges/production.svg)](https://github.com/badges/production.svg)
[![AWS S3 Deployed](https://img.shields.io/badge/Deployed-AWS%20S3-brightgreen.svg)](https://s3.amazonaws.com/your-bucket/)
[![GitHub Actions](https://img.shields.io/badge/CI--CD-GitHub%20Actions-blue.svg)](https://github.com/features/actions)

## 📖 Project Overview

**Simple, elegant CI/CD demonstration** showcasing **automated deployment** from GitHub to **AWS S3** using GitHub Actions.

**Built for job interviews** – Zero-config, production-ready pipeline that deploys a modern static site on every `main` push.

**Key Skills Demonstrated:**
- ✅ GitHub Actions workflows
- ✅ AWS S3 static hosting  
- ✅ Secrets management
- ✅ `--delete` sync for clean deploys
- ✅ Responsive frontend design

## ✨ Features

| Feature | Implementation |
|---------|----------------|
| **Auto-Deploy** | Push to `main` → Instant S3 sync |
| **Clean Sync** | `--follow-symlinks --delete` removes old files |
| **Secure** | AWS credentials via GitHub Secrets |
| **Modern UI** | Responsive landing page with pipeline animation |
| **ap-south-2** | Mumbai region (low latency for APAC) |

## 📱 Live Demo

**Local:** `open index.html`

**Deployed:** `https://your-bucket.s3.ap-south-2.amazonaws.com/` *(Update after first deploy)*

## 🎯 index.html Showcase

**New CI/CD-themed landing page** (replaced irrelevant content):
```
🚀 CI/CD Practice Project
├── Badges & Status indicators
├── Pipeline visualization (4-step flow)
├── Feature cards (Zero Config, S3 Sync, etc.)
├── Deploy button (animation demo)
└── Responsive design
```

![Landing Page Preview](https://via.placeholder.com/800x400/3b82f6/ffffff?text=CI/CD+Landing+Page)
*(Actual site renders beautifully!)*

## 🚀 CI/CD Pipeline

**`.github/workflows/deploy.yml`** – Complete workflow:

```yaml
name: Upload Website to S3 bucket
on:
  push:
    branches: [ main ]
jobs:
  deploy:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@master
    - uses: jakejarvis/s3-sync-action@master
      with:
        args: --follow-symlinks --delete  # Clean deploys!
      env:
        AWS_S3_BUCKET: ${{ secrets.AWS_S3_BUCKET }}
        AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
        AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
        AWS_REGION: 'ap-south-2'
        SOURCE_DIR: './'
```

**Visual Flow:**
```
Git Push (main) → GitHub Actions → AWS S3 Sync → ✅ Live!
```

## 🛠️ Tech Stack

```
Frontend:  HTML5/CSS3/Vanilla JS (responsive, animated)
CI/CD:     GitHub Actions + s3-sync-action
Cloud:     AWS S3 (static hosting)
Security:  GitHub Secrets
```

## 📂 Project Structure

```
ci-cd-practice/
├── index.html           # 🚀 CI/CD demo landing page
├── README.md           # 📖 This file!
├── TODO.md             # ✅ Task tracker
└── .github/workflows/
    └── deploy.yml      # 🔄 Auto-deploy pipeline
```

## 🔄 Quick Start

### 🖥️ Local Development
```bash
# Clone & view
git clone your-repo-url
cd ci-cd-practice  
open index.html
```

### ☁️ Deploy to S3 (5 minutes)
```bash
# 1. Create S3 bucket (static website hosting enabled)
# 2. GitHub Repo → Settings → Secrets → Add:
#    AWS_S3_BUCKET=your-bucket
#    AWS_ACCESS_KEY_ID=...
#    AWS_SECRET_ACCESS_KEY=...
# 3. Push to main:
git add .
git commit -m "Deploy CI/CD demo"
git push origin main  # 🚀 Auto-deploys!
```

## 🔐 AWS Setup Guide

1. **S3 Bucket**: Create bucket, enable **Static website hosting**
2. **Bucket Policy**: Public read access
3. **GitHub Secrets**: Add 4 AWS secrets
4. **Push** → Watch [Actions tab](https://github.com/yourusername/ci-cd-practice/actions)

## 💼 Why This Rocks for Jobs

```
✅ Zero dependencies (pure HTML/JS)
✅ Production-grade CI/CD pipeline
✅ AWS + GitHub Actions (in-demand skills)
✅ Clean code & documentation
✅ Works globally (ap-south-2)
✅ Deploy button animation (extra polish!)
```

## 🤝 Next Steps / Enhancements

```
[ ] Add workflow status badge to index.html (dynamic)
[ ] CloudFront CDN integration
[ ] Multi-environment deploys (dev/prod)
[ ] Docker container demo
[ ] Add tests to workflow
```

## 👨‍💻 Author

**Gunar**  
*Full-Stack Developer | DevOps Enthusiast*  
**Portfolio:** gunar.dev | **Email:** gunar@example.com

---

**⭐ Star if useful!**  
**🚀 Deploy it yourself – takes 5 minutes!**

**License:** MIT License

