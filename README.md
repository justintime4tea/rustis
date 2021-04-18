# rustis

[![dependency status](https://deps.rs/repo/github/justintime4tea/rustis/status.svg)](https://deps.rs/repo/github/justintime4tea/rustis)
[![Build Status](https://github.com/justintime4tea/rustis/workflows/CI/badge.svg)](https://github.com/justintime4tea/rustis/actions?workflow=CI)

Yet another redis GUI but this time in rust...

## Getting started

At this point you probably wouldn't want to... but if you did want to then stick around and maybe some documentation will appear in the future.

### Testing locally

`cargo run --release`

On Linux you need to first run `sudo apt-get install libxcb-render0-dev libxcb-shape0-dev libxcb-xfixes0-dev`.

### Compiling for the web

You can compile rustis to [WASM](https://en.wikipedia.org/wiki/WebAssembly) and publish it as a web page. For this you need to set up some tools. There are a few simple scripts that help you with this:

``` sh
./setup_web.sh
./build_web.sh
./start_server.sh
open http://127.0.0.1:8080/
```

* `setup_web.sh` installs the tools required to build for web
* `build_web.sh` compiles your code to wasm and puts it in the `docs/` folder (see below)
* `start_server.sh` starts a local HTTP server so you can test before you publish
* Open http://127.0.0.1:8080/ in a web browser to view

The finished web app is found in the `docs/` folder (this is so that you can easily share it with [GitHub Pages](https://docs.github.com/en/free-pro-team@latest/github/working-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)). It consists of three files:

* `index.html`: A few lines of HTML, CSS and JS that loads rustis.
* `your_crate_bg.wasm`: What the Rust code compiles to.
* `your_crate.js`: Auto-generated binding between Rust and JS.

## egui
You can test the template app at <https://emilk.github.io/egui_template/>.

An egui template project has been used to "seed"/create this project. As of 2021, egui is in active development with frequent releases with breaking changes. [egui_template](https://github.com/justintime4tea/rustis/), from which this project has been seeded from, will be updated in lock-step to always use the latest version of egui.
