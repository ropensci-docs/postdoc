# Generate HTML reference manual

Renders complete package reference manual in HTML format.

## Usage

``` r
render_package_manual(package, outdir = ".", link_cb = r_universe_link)

render_base_manuals(outdir = ".")

r_universe_link(package)
```

## Arguments

- package:

  name of the package

- outdir:

  where to put the html file

- link_cb:

  callback function which can be used to customize hyperlinks to other
  packages. This function gets invoked when a help file contains links
  to another package, and should return the URL to the html reference
  manual for this other package. Set to `NULL` to drop cross-package
  links.

## Value

path to the generated html document

## Details

Math rendering and syntax highlighting are done server-side in R such
that no JavaScript libraries are needed in the browser, which makes the
documents portable and fast to load.

## Examples

``` r
htmlfile <- render_package_manual('compiler', tempdir())
if(interactive()) utils::browseURL(htmlfile)
```
