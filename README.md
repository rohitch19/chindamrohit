
# Personal Portfolio (GitHub Pages)

This is a ready-to-deploy static site. Update `data/site.json` with your info, then push to GitHub.

## Structure
```
/index.html
/data/site.json
/assets/
  profile.png, project-*.png, og-image.png, favicon-32.png, apple-touch-icon.png, Rohit_Resume.pdf
/404.html
/.nojekyll
```

## Publish on GitHub Pages
1. Create a new repo and upload all files from this folder.
2. Commit & push.
3. In **Settings → Pages**, set:
   - **Branch**: `main`
   - **Folder**: `/ (root)`
4. Open your site once it builds.

## Custom domain (GoDaddy)
- Add a **CNAME** record in GoDaddy to point your domain to `<your-username>.github.io`.
- In the repo root, create a file called `CNAME` containing your domain (e.g. `www.yourdomain.com`).
- Save and push.

## Edit content
- Change text, links, and sections in `/data/site.json`.
- Replace images in `/assets/`.
- Replace `assets/Rohit_Resume.pdf` with your real resume.

## Contact form (Google Forms)
- The form is wired to Google Forms via `forms.google.id` and `fields.entry.*` in `site.json`.
- In Google Forms, turn **off** “Restrict to users in your organization” and **off** “Limit to 1 response”.
- Ensure **Responses** are enabled.
