# Two Birds Project Template

Template repo every new Two Birds Innovation product clones from. Ensures a consistent accessibility + SEO + sovereignty baseline from day one.

## What this repo is

A canonical starting point with the HAL Stack rigor-audit patterns pre-installed:

- Static HTML/CSS/JS scaffold (no npm, no build step, no frameworks)
- `AUDIT.md.template` for first-audit conformity
- `CLAUDE.md` with the standing rules inherited by every product
- Self-hosted Inter font (SIL-OFL) — no Google Fonts
- `css/tokens.css` with a Warm-Hearth-style neutral palette (override per product)
- GitHub Actions workflows: axe-core every-push a11y check, weekly broken-external-link check
- `robots.txt` + `sitemap.xml` scaffolds with 11 AI-bot allow-list (Googlebot, GPTBot, anthropic-ai, PerplexityBot, Claude-Web, ClaudeBot, Google-Extended, CCBot, cohere-ai, Meta-ExternalAgent, Bingbot)
- Skip-link + main landmark scaffold
- en-CA lang attribute + Canadian-English copy conventions

## How to use it

1. Clone this repo under a new name (`git clone` + rename remote)
2. Update `CLAUDE.md` + `README.md` with the new product name
3. Override `css/tokens.css` palette if the product has distinct brand colours
4. Write the product-specific `index.html` / pages
5. Run the first axe-core CI on a PR — should pass out of the box
6. Produce the product's first `AUDIT.md` from the template

## Stack

Vanilla HTML/CSS/JS per the Two Birds no-npm standing rule. Every template file is token-driven + sovereignty-compliant; products should inherit rather than redefine.

## Related repos

- `two-birds-portfolio` — master governance; this template mirrors those rules
- Existing products that inherit from earlier versions of this template: `aaron-patzalek`, `clarity`, `career-coach`, `quality-dashboard`, `two-birds-command-centre`, `kevins-apartment-search`, `two-birds-innovation`

## Model lock note

When running Claude Code sessions, use `claude-sonnet-4-6` (current Sonnet) or `claude-opus-4-7`. Retired Sonnet-4 variants do not resolve.

## License

All template content owned by Two Birds Innovation / Aaron Patzalek. Products that clone this template inherit ownership; they are not obligated to redistribute the template.
