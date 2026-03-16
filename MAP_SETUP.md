# Map Setup for Expertisepunt Website

The map on the home page shows **Expertisepunt, Utrechtseweg 88, 3702 AD Zeist**.

## Current Solution: OpenStreetMap (Free, No Setup)

The site uses an **OpenStreetMap embed** by default. No API key or account is required. It works immediately.

## Alternative: Google Maps API (Free Tier)

If you prefer Google Maps:

### 1. Get a free API key

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project (or select existing)
3. Enable **Maps JavaScript API**: APIs & Services → Library → search "Maps JavaScript API" → Enable
4. Create credentials: APIs & Services → Credentials → Create Credentials → API Key
5. (Recommended) Restrict the key: Edit key → Application restrictions → HTTP referrers → add your domain(s), e.g. `expertisepunt.com/*`, `localhost:*`

### 2. Free tier

- **$200/month** free credit (covers ~28,000 map loads)
- Or from March 2025: **$3,250/month** free credit
- A small site like this typically stays within the free tier
- **Billing must be enabled** (card required) but you won't be charged if you stay within limits

### 3. Add the key to the site

Replace the OpenStreetMap iframe in `index.html` with the original Divi map structure and add your key to the script URL:

```html
<script src="https://maps.googleapis.com/maps/api/js?v=3&key=YOUR_API_KEY&ver=4.27.5" ...></script>
```

Search for `et_pb_fullwidth_map_0` in index.html to find the map section.
