# Blog Publishing Workflow

Quick guide for adding blog posts to Dr. Ajay Agrawal Clinic website.

---

## Adding a New Blog Post

### Step 1: Create the Post

1. Copy `TEMPLATE.html` → `your-post-slug.html`
2. Use lowercase slugs with hyphens (e.g., `diabetes-management-tips.html`)

### Step 2: Update Placeholders

Replace all `[PLACEHOLDER]` values in the template:

| Placeholder | Example |
|-------------|---------|
| `[ARTICLE_TITLE]` | Diabetes Management Tips for Daily Life |
| `[SLUG]` | diabetes-management-tips |
| `[META_DESCRIPTION]` | Practical tips for managing diabetes... (150-160 chars) |
| `[IMAGE_NAME]` | diabetes-management (without .webp) |
| `[YYYY-MM-DD]` | 2025-01-12 |
| `[CATEGORY]` | Diabetes Care |

### Step 3: Add Featured Image

1. Create/get image (1200x630 recommended)
2. Convert to WebP format
3. Save to `/assets/img/blog/[IMAGE_NAME].webp`
4. Keep file size under 100KB for performance

### Step 4: Write Content

- **Intro**: 2-3 sentences hook
- **TL;DR box**: 3-5 key points
- **Hindi summary**: ~50 words (use Google Translate + review)
- **Main sections**: Use H2 for each section
- **CTA section**: Customize for the topic

### Step 5: Update Blog Index

Add a card to `blog/index.html`:

```html
<article class="bg-white rounded-lg shadow border overflow-hidden">
  <a href="/blog/[SLUG].html">
    <img src="/assets/img/blog/[IMAGE_NAME].webp" alt="[IMAGE_ALT]" class="w-full" />
  </a>
  <div class="p-4">
    <a href="/blog/[SLUG].html">
      <h2 class="text-lg font-semibold">[TITLE]</h2>
    </a>
    <p class="text-sm text-gray-600 mt-1">[EXCERPT]</p>
    <div class="text-xs text-gray-500 mt-2">By Dr. Ajay Agrawal • [DATE] • [READ_TIME]</div>
  </div>
</article>
```

### Step 6: Update Sitemap

Add to `/sitemap.xml`:

```xml
<url>
  <loc>https://dr-ajay-agrawal.netlify.app/blog/[SLUG].html</loc>
  <lastmod>[YYYY-MM-DD]</lastmod>
  <changefreq>monthly</changefreq>
  <priority>0.8</priority>
</url>
```

### Step 7: Deploy

1. Commit changes
2. Push to main branch
3. Netlify auto-deploys

### Step 8: Post-Deploy

- [ ] Verify page loads correctly
- [ ] Test schema with [Rich Results Test](https://search.google.com/test/rich-results)
- [ ] Submit sitemap in Search Console (optional - auto-crawl works too)

---

## Schema Checklist

Each blog post should have:

- [x] `BlogPosting` schema with correct image URL
- [x] `BreadcrumbList` schema for SERP breadcrumbs
- [x] Canonical URL
- [x] Open Graph meta tags
- [x] Twitter Card meta tags

---

## Image Guidelines

| Requirement | Value |
|-------------|-------|
| Format | WebP preferred |
| Dimensions | 1200×630 (16:9) |
| Max size | 100KB |
| Alt text | Descriptive, keyword-rich |

---

## Content Guidelines

- **Length**: 800-1500 words ideal
- **Reading level**: 8th grade (accessible)
- **Hindi summary**: Always include
- **CTAs**: Call button + Message button
- **Related posts**: Link 2-3 other articles
