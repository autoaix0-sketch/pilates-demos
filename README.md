# pilates-demos

Public portfolio of Khaireddine Sakkal's pilates website demos.
Live: https://autoaix0-sketch.github.io/pilates-demos/

**Do not edit `demos/` or `demos.json` by hand.** They are generated from the private
`pilates` repo by `python3 tools/publish_demos.py` (then `python3 tools/shots.py`).

## Add a demo
1. In the private repo, make sure the studio is fictional and its `studio.json` has `"public": true`
   (or, for an old single file, it lives in `demos/`).
2. Add an entry to `tools/public_demos.json`.
3. Run `python3 tools/publish_demos.py`, then `python3 tools/shots.py`, then `python3 tools/qa_site.py`.
4. In `public-site/`: `git add -A && git commit -m "Add <name> demo" && git push`.

## Connect a real domain later
1. Buy the domain (e.g. at Namecheap, Porkbun or Cloudflare).
2. Create a file `CNAME` in this repo with one line: the domain (e.g. `www.example.com`). Push.
3. At the domain seller, add a `CNAME` record: `www` → `autoaix0-sketch.github.io`.
   For the bare domain, add `A` records to 185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153.
4. GitHub → repo → Settings → Pages: enter the domain, wait for the check, tick "Enforce HTTPS".

`.gitignore` is an allowlist: only `index.html`, `demos.json`, `README.md`, `demos/**/index.html`, `demos/**/media/*.{mp4,webm,webp}` and `img/*.webp` can be committed. Add new file types there on purpose.
