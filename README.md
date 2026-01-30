 (cd "$(git rev-parse --show-toplevel)" && git apply --3way <<'EOF' 
diff --git a/README.md b/README.md
index 452d89086cdb158a2b7b1a607f9e42c29d692f00..27fde78159146d40d2c413e9e7376f9493fb221b 100644
--- a/README.md
+++ b/README.md
@@ -1 +1,73 @@
-# foraging-ie
\ No newline at end of file
+# Foraging.ie
+
+A starter Astro site for Foraging.ie with a simple content setup for events, books, and blog posts.
+
+## Quick start
+
+```bash
+npm install
+npm run dev
+```
+
+Then open the preview link from Astro.
+
+## Updating content (no code)
+
+All editable content lives in `src/content` as plain markdown files:
+
+- **Events** → `src/content/events`
+- **Books** → `src/content/books`
+- **Blog posts** → `src/content/blog`
+
+Duplicate an existing file and change the details at the top (the **frontmatter**).
+
+Example event frontmatter:
+
+```yaml
+---
+title: "Summer Foraging Walk"
+location: "Howth, Dublin"
+date: 2024-07-10
+bookingUrl: "https://your-booking-link"
+---
+```
+
+## Pages
+
+The main pages live in `src/pages`:
+
+- `/` home page
+- `/events`
+- `/map`
+- `/books`
+- `/blog`
+- `/contact`
+
+You can edit the text in those files to change headings or add embeds.
+
+## Next steps
+
+- Replace the map placeholder in `src/pages/map.astro` with a Google Maps or OpenStreetMap embed.
+- Replace the contact form in `src/pages/contact.astro` with a Formspree or Tally embed.
+- Swap the book `buyUrl` links with Shopify, Gumroad, Lemon Squeezy, or Stripe payment links.
+
+## Deploy to Cloudflare Pages (visual step-by-step)
+
+This project is **not deployed yet**. To make it live, follow these steps:
+
+1. Go to **Cloudflare Dashboard → Pages**.
+2. Click **Create a project** → **Connect to Git**.
+3. Select the GitHub repo **`foraging-ie`**.
+4. Use these build settings:
+   - **Framework preset:** Astro
+   - **Build command:** `npm run build`
+   - **Build output directory:** `dist`
+5. Click **Save and Deploy**.
+
+After it finishes, Cloudflare will give you a live URL. Open that URL to see the site.
+
+### Optional: connect your custom domain
+
+1. In your Pages project, go to **Custom domains**.
+2. Add **`foraging.ie`** and follow the prompts.
+3. Cloudflare will set DNS automatically if your domain is on Cloudflare.
 
EOF
)
