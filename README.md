# Bucket Viewer

A lightweight, standalone browser-based viewer for publicly listable object-storage buckets.

## What It Does

Bucket Viewer converts public object-storage listings into a more usable folder-style interface.

Supported storage types include:

- Amazon S3
- Google Cloud Storage
- Azure Blob Storage
- S3-compatible and custom object-storage endpoints

The viewer can:

- Automatically detect common bucket and storage URL formats
- Enumerate publicly listable objects
- Handle listing pagination
- Convert flat object keys into a folder-style tree
- Display object size and modification time
- Preview common text, source-code, image, PDF, audio, and video formats
- Open raw objects
- Download objects
- Copy object URLs

## Browser / CORS Extension Requirement

Many public buckets can be opened directly in a browser but do not allow JavaScript running from another website to read their responses because of browser CORS enforcement.

Bucket Viewer therefore requires a CORS-relaxing browser extension for endpoints that do not provide the necessary CORS headers.

An extension similar to **Allow CORS: Access-Control-Allow-Origin** should work:

https://chromewebstore.google.com/detail/allow-cors-access-control/lhobafahddgcelffkeicbaginigeejlf?hl=en

Bucket Viewer has been **tested successfully in both Google Chrome and Mozilla Firefox** using this style of CORS extension.

Enable the CORS extension before loading a bucket. Disable it again when you are finished.

The exact extension and controls may vary by browser. The important requirement is that the extension allows the viewer to make cross-origin requests to the public bucket endpoint.

## Usage

1. Open Bucket Viewer.
2. Enable your CORS-relaxing browser extension.
3. Paste the authorized public bucket or container URL.
4. Click **Detect & Load**.
5. Browse the resulting folder and file tree.
6. Select an object to preview it or open/download the raw object.
7. Disable the CORS extension when finished.

## Local Use

The application consists of a single `index.html` file and does not require a backend or local web server.

Open `index.html` directly in a supported browser, enable your CORS-relaxing extension, and load the bucket URL.

## Repository Structure

```text
bucket-viewer/
├── index.html
├── README.md
├── LICENSE
└── .gitignore
```

Only `index.html` is required to run the application.

## Important Notes

The CORS extension only changes browser-side CORS enforcement. It does **not** grant access to objects or bucket functionality that is not already publicly available.

The bucket or container must permit anonymous listing for automatic enumeration to work.

A bucket that permits public access to individual objects but denies anonymous listing cannot be automatically enumerated by Bucket Viewer.

