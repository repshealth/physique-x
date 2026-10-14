# Physique X

The Physique X landing page, as one self-contained HTML file.

## What is in here

| File | What it is |
| --- | --- |
| `index.html` | The whole page. Every image is embedded, so this one file is the site. |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are rather than running them through Jekyll. |
| `CNAME.example` | Rename to `CNAME` only if you point a custom domain at this repo. |

## Putting it live on GitHub Pages

1. Unzip this folder on your computer. GitHub does not unpack a zip for you, so upload the files inside it rather than the zip itself.
2. Create a repository, or open the one you want to use.
3. Click **Add file**, then **Upload files**, and drag in `index.html` and `.nojekyll`. Commit.
4. Go to **Settings**, then **Pages** in the left sidebar.
5. Under **Build and deployment**, set **Source** to *Deploy from a branch*, pick the `main` branch and the `/ (root)` folder, and press **Save**.
6. Wait a minute or two. The page appears at `https://<your-username>.github.io/<repo-name>/`.

Pages serves `index.html` automatically, so the address needs no filename on the end.

## Using your own domain

1. Rename `CNAME.example` to `CNAME` and put your domain in it on a single line, with no `https://` and no trailing slash. For example: `www.physique-x.com`
2. Upload it alongside `index.html`.
3. At your domain registrar, add a `CNAME` record pointing `www` at `<your-username>.github.io`.
4. Back in **Settings**, then **Pages**, tick **Enforce HTTPS** once the certificate has been issued. That can take up to an hour.

## Making changes later

Open `index.html` in any text editor. The styles sit in a `<style>` block near the top and the content follows in plain HTML.

**The enquiry form.** Near the bottom of the file, inside the `<script>` block, two lines need filling in:

- `PX_LEADS_ENDPOINT` is the REPS dashboard address with `/api/forms` on the end, for example `https://dashboard.your-account.workers.dev/api/forms`. Leads then appear in Physique X > Leads. Left empty, the form validates and shows the thank-you but saves nothing.
- `PX_WHATSAPP` is Kieran's number in full international format, digits only, no plus and no leading zero. A UK mobile `07123 456789` becomes `447123456789`. Left empty, the thank-you appears without the WhatsApp button.

**The checkout links.** The pricing buttons point at the join pages. Search for `join.physique-x.com` to find them.

## A note on the images

Every photo and app screenshot is stored in the file as base64, each one held once even where the same picture is used in several places. That keeps the whole site to a single file at the cost of a slightly slower first load, since nothing paints until the file has arrived.

If the page ever feels slow, the fix is to pull the images out into an `images/` folder and reference them by filename. The HTML drops to around 55 KB and starts rendering almost immediately while the pictures load behind it.
