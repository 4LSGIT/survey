# 🔐 Static Survey Site

A minimalist, static survey site built with HTML, JavaScript, and Tailwind CSS. Designed to encode simple question/answer forms into shareable URLs, optionally with webhook support.

## ✨ Features

- **Survey Builder UI** (shown if no valid URL param):
  - Input a question
  - Input a correct answer
  - Optional webhook URL (receives submissions as JSON)
  - Generates a shareable link with encoded data

- **Survey UI** (shown if URL contains valid param):
  - Displays the question
  - Input for answer and name
  - On submit:
    - ✅ If correct: success message
    - ❌ If incorrect: failure message + retry + show answer
    - 📤 Optionally posts to the provided webhook

## ⚙️ How It Works

- Question, answer, and optional webhook URL are encoded using:
  - JSON → Base64 → URL-encoded
- Data is passed via a single `?s=...` URL parameter
- On page load:
  - If valid param exists: renders the survey
  - Otherwise: renders the survey builder

## 💅 Styling

Styled using Tailwind CSS to match the aesthetic of [garlic-counter.glitch.me](https://garlic-counter.glitch.me/):
- Dark theme
- Rounded inputs and buttons
- Clean, minimal UI

## 🚀 Hosting

You can deploy this as a static site on [GitHub Pages](https://pages.github.com), Netlify, Vercel, or any static hosting provider.

## 📦 Example Usage

1. Visit the site without parameters
2. Enter your question, answer, and optional webhook
3. Click **Generate Survey Link**
4. Share the generated URL
5. Recipients open the link and take the survey

## 🛠️ Webhook Notes

- Webhooks are optional
- Use a CORS-friendly endpoint like [webhook.site](https://webhook.site)
- Data is sent as a `POST` request with:
  ```json
  {
    "name": "User's name",
    "answer": "User's submitted answer"
  }
 
