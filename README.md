# Vocab Premium v12 — mobile progress persistence fix

Upload/replace in GitHub Pages root:
- index.html
- sw.js
- manifest.json (same manifest content, included for completeness)

Keep existing icons/ folder.

Core fix:
- local progress is saved immediately;
- startup compares local modifiedAt with cloud modifiedAt;
- stale cloud is never blindly applied over newer local progress;
- interrupted iPhone background uploads keep dirty=true;
- dirty local is uploaded on next launch if it is newer;
- a recovery snapshot is saved before any cloud state overwrites local data;
- service worker cache version bumped to vocab-premium-v12.
