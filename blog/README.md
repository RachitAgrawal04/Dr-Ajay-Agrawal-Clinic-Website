# Blog: Publishing Workflow

This folder contains blog posts for "Dr. Ajay Agrawal Clinic". Use this short workflow to add or update posts.

1) Create the post file
- File path: `blog/your-post-slug.html` (use lowercase, hyphens for spaces).
- Copy an existing post (e.g., `preventive-health-checkups-annual.html`) as a template.

2) Required metadata (head section)
- title, canonical, description, keywords
- Open Graph / Twitter meta (og:title, og:description, og:image)
- JSON-LD `BlogPosting` schema with:
  - headline, description, image, datePublished, dateModified, author (Dr. Ajay Agrawal), mainEntityOfPage

3) Featured image
- Prefer self-hosted images in `/assets/img/blog/` (webp + fallback).
- Provide responsive images using `srcset` and `loading="lazy"`.
- If you temporarily use Unsplash hotlinks, later replace with local files for reliability and performance.

4) Hindi summary (required)
- Add a short Hindi summary block near the top of each post using the snippet in `hindi-summaries.html` (or copy the small snippet below). Use `lang="hi"` and a clear heading (e.g., "संक्षेप (हिंदी)").

5) Blog index
- Add/update `blog/index.html` card for the new post:
  - image, title, excerpt, author/date, read time.
  - Link to the new post URL.

6) Sitemap & robots
- Update `sitemap.xml` to include the new post URL and `lastmod` of the update.
- Ensure `robots.txt` references `sitemap.xml`.

7) Accessibility & SEO checklist
- Alt text for images (descriptive).
- Add `rel="canonical"` in head pointing to the post URL.
- Use one H1 per page; use H2/H3 for structure.
- Ensure the JSON-LD validates in Google's Rich Results Test.

8) Commit & PR
- Branch naming: `blog/<slug>` or `blog-launch/<date>` (example: `blog/diabetes-care`).
- PR title: `Add blog: <Post Title>` with a short summary.
- Include screenshots if the post layout uses special images or embeds.

9) After merge
- Submit the updated sitemap in Google Search Console (or wait for auto-crawl).
- Optionally create a Google Business Profile post linking to the new article.

If you’d like, I can:
- Open a PR that adds the README and Hindi summaries + update robots.xml/sitemap.
- Convert Unsplash images to compressed local images and update `srcset`.
