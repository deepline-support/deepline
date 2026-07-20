# Deepline Support / Aspen

This package is arranged so that a GitHub Pages site using the custom domain
`deepline.support` serves the videos at:

`https://deepline.support/aspen/`

## Replace the placeholder media

Put your files here, using these exact names:

- `aspen/media/video-1.mp4`
- `aspen/media/video-2.mp4`
- `aspen/media/video-3.mp4`
- `aspen/subtitles/video-1-en.vtt`
- `aspen/subtitles/video-2-en.vtt`
- `aspen/subtitles/video-3-en.vtt`

The included `.vtt` files are placeholders and must be replaced.

You can change the visible titles by editing `aspen/index.html`:
- Video One
- Video Two
- Video Three

## Publish with GitHub Pages

1. Create a PUBLIC GitHub repository. A user-site repository named
   `YOUR-USERNAME.github.io` is the simplest arrangement for a custom root domain.
2. Upload all contents of this package to the repository root.
3. Open repository **Settings > Pages**.
4. Under **Build and deployment**, select **Deploy from a branch**.
5. Select branch **main**, folder **/(root)**, then save.
6. In the Pages **Custom domain** box, enter `deepline.support` and save.
7. Configure the DNS records shown in GitHub's documentation at your domain provider.
8. When GitHub's DNS check succeeds, enable **Enforce HTTPS**.

## Important path/domain rule

A DNS record cannot target only `/aspen`. The whole hostname `deepline.support`
must point to this GitHub Pages site. The `aspen` folder then creates the `/aspen/`
URL.

If the existing root domain must stay on another host, use a subdomain such as
`aspen.deepline.support` instead, or configure the existing host to proxy/redirect
that path.

## Video size warning

GitHub blocks ordinary Git files above 100 MiB, and browser uploads are limited
to 25 MiB per file. GitHub Pages also has a published-site size limit. Compress
large videos before upload or host the MP4 files on a suitable object/video host
and replace the `src` URLs in `aspen/index.html`.

## Editing the overview text

Open `aspen/index.html` and replace:
- the paragraph with class `page-overview`
- each paragraph with class `video-overview`

Subtitles are marked `default` in HTML and are also switched to `showing` by JavaScript when each video loads. Browser/user accessibility settings can still override caption display.
