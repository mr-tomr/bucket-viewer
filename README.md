# Bucket Viewer

A standalone browser-based viewer for publicly listable object-storage buckets.

Live GitHub Pages site:

https://mr-tomr.github.io/bucket-viewer/

Repository:

https://github.com/mr-tomr/bucket-viewer

## What it does

Bucket Viewer converts public object-storage listings into a more usable folder-style interface.

Supported storage types include:

- Amazon S3
- Google Cloud Storage
- Azure Blob Storage
- S3-compatible/custom object-storage endpoints

The viewer can:

- Automatically detect common bucket/storage URL formats
- Enumerate publicly listable objects
- Handle listing pagination
- Convert flat object keys into a folder-style tree
- Display object size and modification time
- Preview common text, source-code, image, PDF, audio, and video types
- Open raw objects
- Download objects
- Copy object URLs

## Browser / CORS Extension Requirement

Many public buckets can be opened directly in a browser but do not allow JavaScript on another website to read their responses because of browser CORS enforcement.

Bucket Viewer therefore requires a CORS-relaxing browser extension for those endpoints.

An extension similar to **Allow CORS: Access-Control-Allow-Origin** should work:

https://chromewebstore.google.com/detail/allow-cors-access-control/lhobafahddgcelffkeicbaginigeejlf?hl=en

The viewer has been **tested successfully in Firefox** using this style of CORS extension.

Enable the extension before loading a bucket and disable it again when finished.

The exact extension and controls may vary by browser. The important requirement is that it allows the viewer to make cross-origin requests to the public bucket endpoint.

## Use the GitHub Pages Version

Open:

https://mr-tomr.github.io/bucket-viewer/

Then:

1. Enable your CORS-relaxing browser extension.
2. Paste the authorized public bucket/container URL.
3. Click **Detect & Load**.
4. Browse the folder/file tree.
5. Disable the CORS extension when finished.

## Run Locally

No web server is required.

Download the repository and open either:

```text
index.html
```

or:

```text
public_bucket_viewer_requires_cors_extension.html
```

directly in your browser.

Then enable your CORS-relaxing extension and use the viewer normally.

## GitHub Pages Setup

This repository is configured to use `index.html` as the GitHub Pages entry point.

To enable Pages:

1. Open the repository on GitHub.
2. Go to **Settings**.
3. Select **Pages**.
4. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
5. Select branch **main**.
6. Select folder **/(root)**.
7. Click **Save**.

The published site will be:

https://mr-tomr.github.io/bucket-viewer/

## Files

- `index.html` — GitHub Pages homepage
- `public_bucket_viewer_requires_cors_extension.html` — descriptively named standalone copy
- `README.md` — project documentation
- `.gitignore` — basic repository ignores
- `LICENSE` — MIT license

## Important Notes

The CORS extension only changes browser-side CORS enforcement. It does **not** grant storage permissions.

The bucket/container must already permit anonymous listing for automatic enumeration to work.

A bucket that permits public access to individual objects but denies anonymous listing cannot be automatically enumerated by this viewer.

Use only against buckets and containers you are authorized to assess.
