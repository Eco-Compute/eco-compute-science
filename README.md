# ecoCompute Science

Website for **ecoCompute Science**, a peer-reviewed, artifact-first venue for resource aware
computing. Summer 2027, online.

The site also hosts the archive of the former **ecoCompute conference** (Munich 2024, Berlin
2025) under `/previous-years`.

Built with [Hugo](https://gohugo.io/) using a heavily modified version of the *Vixcon* theme
(<https://docs.gethugothemes.com/vixcon/installation/>).

## Building

```bash
hugo            # build into ./public
hugo server     # local preview on http://localhost:1313
```

No `npm` packages need to be installed. Deployment happens from `main` via
`.github/workflows/hugo.yml`.

## Where to edit what

Most editing happens in YAML data files, not in Markdown.

| What | Where |
| --- | --- |
| The whole landing page | `data/en/homepage.yml` |
| FAQ entries | `data/en/faq.yml` |
| The conference archive index | `data/en/previous_years.yml` |
| Archived 2024/2025 schedule | `data/en/schedule.yml` |
| Navigation, site title, contact address, analytics domain | `config.toml` |
| About, Call for Papers, Artifacts, Review & Publication, Code of Conduct, legal | `content/english/*.md` |

The landing page template is `themes/vixcon-hugo/layouts/index.html`. It reads
`data/en/homepage.yml` section by section, and every section has an `enable` flag.

Venue specific styling lives in `themes/vixcon-hugo/assets/scss/_science.scss`, which is
imported **last** from `style.scss` so that it wins over the generic theme rules above it.

## Things that still need filling in

These are deliberately marked as open on the site rather than faked:

- Submission dates, and the submission system itself (`content/english/call-for-papers.md`)
- The journal hosting stage two publication (`data/en/homepage.yml`, `status:` block)
- The second, industry and impact track
- Programme committee and artifact evaluation committee members
- Named Code of Conduct contacts (`content/english/code-of-conduct.md`)
- **A photo of Anna-Lena Lamprecht.** `static/images/teams/anna-lena-lamprecht*.webp`
  is currently a monogram placeholder reading "photo to follow". Replace the three
  files with a square portrait at 900x900 (`-900.webp`), 450x450 (`-450.webp`) and
  the base `anna-lena-lamprecht.webp`, and the organisers grid picks it up with no
  template change. The other two organisers use their photos from the 2025
  conference.
- Submission system, video platform and LLM provider in the privacy policy
  (`content/english/datenschutz.md`)

## The archive

Everything under `/previous-years`, `/schedule/{2024,2025}`, `/speakers/*`, `/talks/*` and
`/workshops/*` belongs to the old in-person conference. Those pages carry
`outdated: true` in their front matter, which renders the banner in
`themes/vixcon-hugo/layouts/partials/archive-notice.html`.

Do not add new content there.

## Redirects

`static/_redirects` is copied into `public/` on build and maps the old conference URLs
(tickets, sponsoring, grants, ...) onto the archive. Note that this file is only honoured by
Cloudflare Pages, not by GitHub Pages.

## Link checking

With `hugo server` running:

```bash
python3 check_404.py
```

`/speaker/<name>/` results are expected: they are handled by `static/_redirects` in
production, which the local server does not apply.
