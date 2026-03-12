# AI Scraping Protection - Implementation Guide

This portfolio includes comprehensive protections against AI bot scraping and unauthorized use for machine learning training.

## Files Added

### 1. `robots.txt`
- Blocks major AI crawlers (GPTBot, Claude, CCBot, Google-Extended, etc.)
- Allows legitimate search engines (Google, Bing, DuckDuckGo)
- Place in your website root directory

### 2. `AI-TRAINING-RESTRICTION.txt`
- Legal notice prohibiting AI training on your content
- Copyright and usage terms
- Clear enforcement policy
- Consider linking to this from your footer or about page

### 3. `.htaccess` (for Apache servers)
- Server-level bot blocking
- HTTP headers that signal "noai" directives
- Returns 403 Forbidden to blocked bots
- **Note:** Only works on Apache servers. If using Nginx, GitHub Pages, or other hosting, you'll need different configuration.

### 4. HTML Meta Tags
Already added to `solar-jewel-main.html`:
```html
<meta name="robots" content="noai, noimageai">
<meta name="googlebot" content="noai, noimageai">
<meta name="googlebot-news" content="nosnippet">
```

## To Complete Protection

### Apply to All HTML Files
Add these meta tags to the `<head>` section of every HTML page:

```html
<!-- Prevent AI bot scraping -->
<meta name="robots" content="noai, noimageai">
<meta name="googlebot" content="noai, noimageai">
<meta name="googlebot-news" content="nosnippet">
```

Files that likely need updating:
- `index.html`
- `work.html`
- `about.html`
- Any other HTML pages

### Upload Files
1. Upload `robots.txt` to your website root
2. Upload `.htaccess` to your website root (if using Apache)
3. Upload `AI-TRAINING-RESTRICTION.txt` to your website root
4. Update all HTML files with the meta tags

### For GitHub Pages
If hosting on GitHub Pages:
- `robots.txt` will work automatically
- `.htaccess` won't work (GitHub Pages uses nginx)
- Meta tags will work
- Consider adding a visible copyright notice

### Optional: Add Visible Notice
Consider adding a copyright notice to your footer:

```html
<footer>
    <p>© 2026 Anya Traille. All Rights Reserved. 
    <a href="AI-TRAINING-RESTRICTION.txt">AI Training Prohibited</a></p>
</footer>
```

## Effectiveness

### What These Protections Do:
✅ Block respectful AI bots that honor robots.txt  
✅ Provide legal standing for copyright claims  
✅ Signal to search engines not to use content for AI  
✅ Create clear terms of use  

### Limitations:
❌ Cannot block all bots (some ignore robots.txt)  
❌ No technical way to prevent all scraping  
❌ Legal enforcement may be needed for violations  
❌ Bots could use residential IPs to bypass blocks  

### Best Practices:
- Regularly update your robots.txt with new bot user agents
- Monitor your server logs for suspicious activity
- Consider adding watermarks to important images
- Keep documentation of your copyright notices
- Stay informed about AI scraping legal developments

## Testing

### Verify robots.txt:
Visit: `https://your-domain.com/robots.txt`

### Check Meta Tags:
View source on your pages and confirm tags are present

### Test Headers (if using .htaccess):
Use curl: `curl -I https://your-domain.com`
Look for: `X-Robots-Tag: noai, noimageai`

## Resources

- [Google's noai directive](https://developers.google.com/search/docs/crawling-indexing/robots-meta-tag)
- [Dark Visitors - AI Bot Directory](https://darkvisitors.com/)
- [Spawning AI - Artist Rights Tools](https://spawning.ai/)

## Updates

Last updated: March 12, 2026

As new AI crawlers emerge, update your `robots.txt` and `.htaccess` files accordingly.
