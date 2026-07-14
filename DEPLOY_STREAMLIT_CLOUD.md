# Deploy to Streamlit Community Cloud

This guide helps you deploy this app so other users can access it online.

## 1) Push to GitHub

1. Create a GitHub repository.
2. Push this project to the repository.
3. Make sure sensitive files are NOT committed (.env, secrets files).

## 2) Confirm required files

- `Sevenz.py` (main app)
- `requirements.txt` (Python dependencies)

Optional but recommended:
- `.gitignore`

## 3) Create Streamlit Cloud app

1. Open https://share.streamlit.io/
2. Sign in with GitHub.
3. Click **New app**.
4. Select your repository and branch.
5. Set **Main file path** to: `Sevenz.py`
6. Click **Deploy**.

## 4) Add secrets/environment values

In Streamlit Cloud app settings, open **Secrets** and add keys if needed:

```toml
OPENAI_API_KEY = "your_openai_key"
GEMINI_API_KEY = "your_gemini_key"
SUNO_API_KEY = "your_suno_key"
```

You can add only the providers you actually use.

## 5) Validate after deploy

1. Open the public app URL.
2. Test lyric generation flow.
3. Test Suno flow using **Reset to SunoAPI defaults** button.
4. Confirm generation, status polling, and audio playback.

## 6) Common fixes

- Build fails on dependency:
  - Recheck package versions in `requirements.txt`.
- API 401 errors:
  - Verify key in Streamlit Secrets.
  - Use raw key value (do not include `Bearer ` prefix).
- Suno returns HTML instead of JSON:
  - Ensure Base URL is `https://api.sunoapi.org`.

## 7) Share with others

After successful deploy, share the Streamlit app URL.
