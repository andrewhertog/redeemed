# redeemed.ca

A small static site setting out the gospel of Jesus Christ, from a Presbyterian
perspective holding to the Westminster Standards. Built with [Astro](https://astro.build).

## Develop

```sh
npm install
npm run dev      # http://localhost:4321
npm run build    # outputs to dist/
```

## Structure

| Path | Purpose |
| --- | --- |
| `src/pages/index.astro` | The gospel: God, Man, Christ, Response |
| `src/pages/deeper.astro` | The same outline with the Shorter Catechism and WCF |
| `src/pages/*.md` | Bible reading, resources, church finder, about |
| `src/components/` | `Hero` (catechism question), `Part` (reference-Bible layout), `Verse`, `Catechism` |
| `src/styles/global.css` | Colour tokens (light + dark), type, shared styles |

## Content guidelines

- Scripture is quoted from the **ESV**. Stay under 500 verses total; the copyright notice is in the footer.
- Doctrinal pages (`deeper`, the Westminster section of `resources`, `church`, `about`) cite **Westminster sources only**.
  Broadly Reformed (non-dispensational) authors are allowed **only** in "Books for those asking questions".
- Keep the free offer of the gospel (no hyper-Calvinism), and avoid "sinner's prayer" or decision-based assurance language.
- Westminster is the confessional reference point for the site's own teaching. The Three Forms of Unity appear only as
  NAPARC churches on the church page and as text links in resources; don't teach from them elsewhere.
- No dispensational sources (e.g. Grace to You, GotQuestions, Scofield material).

## Deploy (Cloudflare Pages)

1. Push this folder to a GitHub repository.
2. In Cloudflare: **Workers & Pages → Create → Pages → Connect to Git**, choose the repo.
3. Framework preset **Astro**; build command `npm run build`; output directory `dist`.
4. Under **Custom domains**, add `redeemed.ca` (and `www.redeemed.ca`, redirecting to the apex).
