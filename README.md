# inlaysql.github.io

The page served at **<https://inlaysql.github.io>**.

There is no site content in this repository, and that is deliberate. The page
embeds a live demo — it compiles [InlaySQL](https://github.com/inlaySQL/inlaysql)
to WebAssembly and runs real queries in the visitor's browser — so a copy of the
engine committed here would become a lie the moment the engine changed. The
page would keep answering from a build nobody could date.

So [`.github/workflows/publish.yml`](.github/workflows/publish.yml) checks out
`inlaySQL/inlaysql`, builds the WebAssembly module the way that repository's own
`wasm.yml` does, runs the same browser smoke test against the result, and
deploys only if it passes.

**To change the page, edit
[`crates/inlaysql-wasm/www/index.html`](https://github.com/inlaySQL/inlaysql/blob/main/crates/inlaysql-wasm/www/index.html)
in the engine repository** — not here. This repository holds the workflow and
nothing else.

It rebuilds on every push here, weekly on a schedule, and on demand from the
Actions tab. The same page is also served from the engine repository at
<https://inlaysql.github.io/inlaysql/>.
