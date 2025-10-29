# Openhack Guide Redirect

A simple, fast redirect service hosted on Vercel as a **static website** with a beautiful loading animation.

## Why this approach?

- **No cloud functions** - Pure static HTML, CSS, and JavaScript
- **Instant deploys** - No build step needed
- **Fast redirects** - No server-side processing
- **Instant updates** - Changes take effect immediately, no DNS propagation delays
- **Beautiful UX** - Nice loading animation while redirecting

## Setup

### 1. Update the Target URL

Edit `index.html` and change this line:

```javascript
const REDIRECT_URL = 'https://example.com/your-target-path';
```

Replace `https://example.com/your-target-path` with your actual target URL.

### 2. Deploy to Vercel

**Option A: Using GitHub (Recommended)**
1. Push this code to a GitHub repository
2. Go to [vercel.com](https://vercel.com)
3. Click "New Project"
4. Select your repository
5. Click "Deploy" - that's it!

**Option B: Using Vercel CLI**
```bash
npm install -g vercel
vercel
```

**Option C: Drag & Drop**
1. Go to [vercel.com](https://vercel.com)
2. Drag your project folder onto the dashboard
3. Done!

### 3. Point Your Domain

In your domain registrar's DNS settings:
- Add a `CNAME` record pointing to your Vercel deployment
- Or use Vercel's custom domain feature in your project settings
- Configuration typically takes a few minutes

## How It Works

1. Visitor lands on your domain
2. The static HTML page loads with a loading animation
3. After 1 second, the page automatically redirects to your target URL
4. If the redirect fails, visitors can click the fallback button

## Customizing the Animation

You can customize the appearance by editing the `<style>` section in `index.html`:

- **Change colors**: Modify the gradient in the `body` background
- **Change animation speed**: Adjust the `animation: spin 0.8s` value
- **Change redirect delay**: Modify the `setTimeout(1000)` value (in milliseconds)
- **Change the container**: Customize the `.container` styles

## Testing Locally

Simply open `index.html` in your browser to test. The redirect will work after 1 second.

## Monitoring Redirects

Track redirect traffic through:
- Your target domain's analytics (they'll see the referrer)
- Vercel Analytics Dashboard
- Server logs at your target destination

## License

MIT