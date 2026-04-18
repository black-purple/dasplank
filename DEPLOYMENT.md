# DAS PLANK Deployment Configuration

## Custom Domains Setup

The site is currently deployed at: https://dasplank.pages.dev

### To add custom domains (.com and .de):

1. **Go to Cloudflare Dashboard**
   - Visit: https://dash.cloudflare.com/pages
   - Select your "dasplank" project

2. **Add Custom Domains**
   - Click "Custom domains" tab
   - Click "Set up a custom domain"
   - Add `dasplank.com` (or your preferred domain)
   - Add `dasplank.de` (German domain)

3. **Configure DNS**
   Cloudflare will provide DNS records to add:
   - CNAME record pointing to your Pages domain
   - Or direct Cloudflare nameserver setup

4. **SSL/TLS**
   - Cloudflare automatically provisions SSL certificates
   - Enable "Full (strict)" SSL mode for security

### Domain Redirects (Optional)

To redirect one domain to another (e.g., .de → .com):

1. In Cloudflare Pages settings, go to "Redirects"
2. Add rule: `dasplank.de/*` → `https://dasplank.com/:splat`

## GitHub Actions Workflow

The workflow automatically deploys on every push to main branch.

### Required Secrets:
- `CLOUDFLARE_API_TOKEN` - Your Cloudflare API token
- `CLOUDFLARE_ACCOUNT_ID` - Your Cloudflare account ID

### Manual Trigger

You can also manually trigger deployment from:
https://github.com/black-purple/dasplank/actions/workflows/deploy.yml
