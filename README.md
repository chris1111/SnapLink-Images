[![License: GPL v2](https://img.shields.io/badge/License-GPL%20v2-blue.svg)](https://github.com/chris1111/SnapLink-Images/blob/main/LICENSE) [![pages-build-deployment](https://github.com/chris1111/SnapLink-Images/actions/workflows/pages/pages-build-deployment/badge.svg)](https://github.com/chris1111/SnapLink-Images/actions/workflows/pages/pages-build-deployment)
# SnapLink-Images
### Working in macOS and IOS
- Upload any image, preview each one, grab download links individually, or bundle them all into a ZIP.
## Start using SnapLink-Images ➢ [SnapLink-Images](https://chris1111.github.io/SnapLink-Images/)
### SnapLink-Images lets a user:

	◦	upload one or more image files
	◦	preview them locally
	◦	send them to imgbb
	◦	get permanent hosted links back
	◦	copy/download individual links
	◦	download all images or bundle them into a ZIP
  
### Codebase structure
#### At the repo root there are only a few files:
	•	README.md
	•	index.html
	•	license and git metadata files
### So this is essentially a single-file application.
#### Key technologies used
#### From index.html:
	•	HTML for the app structure
	•	CSS embedded in the same file for all styling
	•	Vanilla JavaScript embedded in the same file for all behavior
	•	Tailwind CSS CDN for utility classes
	•	JSZip CDN for ZIP creation in the browser
	•	Font Awesome CDN for icons
	•	Google Fonts for typography
	•	imgbb API for image hosting via fetch(...)
### There is no build system, no framework, and no package manager config like package.json.
#### How the code is organized
#### index.html contains 3 main parts:
- 1. <head>
	•	external CDN imports
	•	large embedded <style> block
	•	theme variables and all component styling
- 2. <body> markup
#### This defines the UI:
	•	decorative background layers
	•	toast container
	•	ZIP progress overlay
	•	lightbox modal for full image preview
	•	hidden file input
	•	upload area
	•	summary/action bar
	•	image gallery container
  
- 3. <script>
#### All app logic lives here.
#### Main JavaScript responsibilities, State
#### The script keeps app state in plain variables:
	•	imageStore — array of uploaded image entries
	•	isUploading — upload lock
	•	idCounter — unique IDs per card
	•	DOM references for buttons, gallery, overlays, etc.
  
### Utilities
#### Helper functions include:
	•	showToast(...) — notifications
	•	fmtSize(...) — file size formatting
	•	ext(...) — file extension display
	•	truncate(...) — shorten filenames
	•	copyText(...) / fallbackCopy(...) — clipboard support
	•	confettiBurst(...) — visual effect
### Upload flow
#### Core upload logic:
	•	handleFiles(...)
	◦	filters to images only
	◦	rejects files over 32 MB
	◦	creates local preview URLs
	◦	uploads files one-by-one
	•	uploadToImgbb(file)
	◦	sends the file to imgbb with fetch
	◦	returns hosted URL data
### Rendering
#### UI card creation/update is split into:
	•	renderCard(entry, delay) — creates a gallery card
	•	updateCardStatus(entry) — updates card when upload succeeds or fails
	•	simulateProgress(id) — fake per-card progress animation
	•	updateSummary() — updates counts and enables/disables bulk actions

- HTML Page Create with help of [Z-AI](https://z.ai)

