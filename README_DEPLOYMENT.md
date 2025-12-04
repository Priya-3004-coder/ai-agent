# Resume Screening Agent - Deployment Guide

## 🚀 Quick Deploy to Streamlit Cloud

[![Open in Streamlit](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://share.streamlit.io/)

## 📋 Prerequisites

- GitHub account
- Google Gemini API key (free): https://makersuite.google.com/app/apikey

## 🔧 GitHub Deployment Steps

### 1. Create GitHub Repository

1. Go to https://github.com/new
2. Create a new repository (e.g., `resume-screening-agent`)
3. Make it **Public** (required for free Streamlit Cloud hosting)
4. Don't initialize with README (we already have one)

### 2. Push Code to GitHub

Open terminal in your project folder and run:

```bash
# Initialize git (if not already done)
git init

# Add all files
git add .

# Commit
git commit -m "Initial commit: Resume Screening Agent"

# Add remote (replace YOUR_USERNAME and YOUR_REPO)
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git

# Push to GitHub
git branch -M main
git push -u origin main
```

### 3. Deploy to Streamlit Cloud

1. Go to https://share.streamlit.io/
2. Click **"New app"**
3. Connect your GitHub account (if not already connected)
4. Select your repository
5. Configure:
   - **Branch**: `main`
   - **Main file path**: `app_gemini_cloud.py`
   - **Python version**: `3.10`
6. Click **"Advanced settings"**
7. Add your API key in **Secrets**:
   ```toml
   GEMINI_API_KEY = "your_api_key_here"
   ```
8. Click **"Deploy"**

### 4. Your App is Live! 🎉

Your app will be available at:
```
https://YOUR_USERNAME-YOUR_REPO-RANDOM.streamlit.app
```

## 📁 Important Files for Deployment

Make sure these files are in your repository:

- ✅ `app_gemini_cloud.py` - Main application
- ✅ `resume_agent_gemini.py` - Core agent logic
- ✅ `requirements_gemini.txt` - Python dependencies
- ✅ `packages.txt` - System dependencies
- ✅ `.streamlit/config.toml` - Streamlit configuration
- ✅ `.gitignore` - Excludes sensitive files
- ✅ `README.md` - Documentation

## 🔐 Security Notes

- ✅ `.env` file is in `.gitignore` (never commit API keys!)
- ✅ Use Streamlit Secrets for API keys in production
- ✅ API keys are encrypted in Streamlit Cloud

## 🐛 Troubleshooting

### Issue: Module not found
**Solution**: Check `requirements_gemini.txt` has all dependencies

### Issue: ChromaDB error
**Solution**: Ensure `packages.txt` exists with system dependencies

### Issue: API key not working
**Solution**: 
1. Verify API key in Streamlit Cloud Secrets
2. Format: `GEMINI_API_KEY = "your_key"`
3. No quotes around the key name

### Issue: App crashes on startup
**Solution**: Check logs in Streamlit Cloud dashboard

## 📊 Usage Limits

**Google Gemini Free Tier:**
- 60 requests per minute
- 1,500 requests per day
- Perfect for demos and small-scale use

## 🔄 Updating Your Deployment

After making changes:

```bash
git add .
git commit -m "Description of changes"
git push
```

Streamlit Cloud will automatically redeploy!

## 📞 Support

- Streamlit Docs: https://docs.streamlit.io/
- Gemini API Docs: https://ai.google.dev/docs
- GitHub Issues: Create an issue in your repository

## 🎓 Demo

Try the live demo: [Your deployed URL here]

## 📝 License

MIT License - Feel free to use and modify!
