# Personal Website (GitHub Pages) — Google Forms Integration

This site can submit contact messages to **Google Forms** or **Formspree**, controlled by `data/site.json`.

## Choose your provider (default: Google Forms)
Edit `data/site.json` → `forms`:

```json
{
  "forms": {
    "provider": "google",
    "google": {
      "id": "YOUR_GOOGLE_FORM_ID",
      "fields": {
        "name": "entry.111111",
        "email": "entry.222222",
        "subject": "entry.333333",
        "message": "entry.444444"
      }
    },
    "formspree": { "endpoint": "https://formspree.io/f/your-code" }
  }
}
```

### How to get the Google Form ID and field names
1. Create your Google Form with fields: **Name**, **Email**, **Subject**, **Message**.
2. Click **Send → Get pre-filled link**. Enter sample values and **Get link**.
3. Copy the generated URL. It will look like:

   `https://docs.google.com/forms/d/e/XXXXXXXXXXXXXXXX/viewform?usp=pp_url&entry.111111=John&entry.222222=john%40mail.com&entry.333333=Hi&entry.444444=Hello`

   - The part after `/d/e/` up to `/viewform` is your **Form ID**.

   - The `entry.xxxxxx` query params are the **field names**. Map them to `name`, `email`, `subject`, `message` in `site.json`.
4. Save the file and push to GitHub. The site will update automatically.

### How it works
- For **Google Forms**: the site posts the form to `https://docs.google.com/forms/d/e/<ID>/formResponse` targeting a hidden iframe. No CORS issues, no page redirect. A success message appears under the form.
- For **Formspree**: uses `fetch` + JSON response with a loading state, validation, and local draft saving.

## Deploy
- Upload `index.html`, `assets/`, and `data/site.json` to your GitHub repo root.
- Enable **Settings → Pages → Deploy from a branch** (Branch: `main`, Folder: `/ (root)`).

## Tips
- Keep the **honeypot** field (named `company`) to reduce spam.
- For dark mode, the Google Forms iframe cannot be themed—you’ll see Google’s default styling only if you embed the full form. This integration keeps your site’s UI but sends data to Google.

© 2025 Chindam Rohit
