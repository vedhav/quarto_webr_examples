# Using shinylive and webR in a quarto document

## Installation and Prerequisites

- Make sure you have quarto installed.

- Install the `shinylive` for both R and python. Note that you have to install the development version of `shinylive` package for R because in order to use both R and python shinylive they must use the same assets.

```r
# install.packages("pak")
pak::pak("posit-dev/r-shinylive")
```

```bash
pip install shinylive
```

- Install the quarto extension for shinylive.

```bash
quarto add quarto-ext/shinylive
```

- Install the quarto extension for WebAssembly powered code blocks in R and Python.

```bash
quarto add r-wasm/quarto-live
```

## Rendering and viewing the content

- Render the document using the following command:

```bash
quarto render
```

Now the `_site` directory will contain all the required static files needed to host and view this content. You can start the static server using any method you prefer. Here are a couple of examples:

- Using Python:

```bash
python3 -m http.server 8000 --directory _site
```

```r
httpuv::runStaticServer(dir = "_site/")
```
