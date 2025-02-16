<!--/*
     *
     * Copyright 2020 Adobe
     * All Rights Reserved.
     *
     * NOTICE: Adobe permits you to use, modify, and distribute this file in
     * accordance with the terms of the Adobe license agreement accompanying
     * it. If you have received this file from a source other than Adobe,
     * then your use, modification, or distribution of it requires the prior
     * written permission of Adobe.
     *
     */-->
# Adobe Coral Spectrum hugo theme

Hugo theme using Adobe [coral-spectrum](https://opensource.adobe.com/coral-spectrum/documentation/) Web Components following Spectrum design patterns.

# Usage

See [exampleSite](exampleSite/) for a sample docs website.

A live demo is available at: [https://opensource.adobe.com/hugo-spectrum/](https://opensource.adobe.com/hugo-spectrum/)


# Maintainers Notice

## Test `exampleSite` using local theme

Run the site using the local theme, i.e. `--theme hugo-spectrum`
which is mapped to local theme folder and not github remote module.

```sh
./docs-local.sh
```

## Update `coral-spectrum` version

This theme is using [adobe/coral-spectrum](https://github.com/adobe/coral-spectrum) Web Components.

To upgrade `coral-spectrum` follow these steps:

```sh
set -e
#get the package tarball url
wget `npm view @adobe/coral-spectrum dist.tarball`
tar xzvf coral-spectrum-*.tgz
cp package/dist/css/coral.min.css static/css/coral.min.css
cp package/dist/js/coral.min.js* static/js/
cp package/dist/resources/spectrum-* static/resources/
rm -rf coral-spectrum-*.tgz package

# commit to git
git add .
git commit
```
See also https://github.com/adobe/coral-spectrum/#using-coral-spectrum for full details.

## Update `mermaid` version
This theme has support for [Mermaid](https://mermaid-js.github.io/mermaid/) diagrams. 
To upgrade `mermaid` follow these steps:

```sh
set -e
#get the package tarball url
wget `npm view mermaid dist.tarball`
tar xzvf mermaid-*.tgz
cp package/dist/mermaid.min.js* static/js/
rm -rf mermaid-*.tgz package

# commit to git
git add .
git commit
```

## Update `markdeep` version
This theme has support for [Markdeep](https://casual-effects.com/markdeep/features.md.html#diagramexamples) diagrams. 
To upgrade `markdeep` follow these steps:

```sh
set -e
#get js
wget https://casual-effects.com/markdeep/latest/markdeep.min.js -O static/js/markdeep.min.js

# commit to git
git add .
git commit
```

## Update `stork` version
This theme has support for [Stork](https://stork-search.net) search. 
To upgrade `Stork` follow these steps:

```sh
set -e

# update version and run
./download-stork.sh 

# commit to git
git add .
git commit
```

## Update `KaTeX` version
This theme has support for [MathJax](https://www.mathjax.org/) math typesetting.
To upgrade `MathJax` follow these steps:

```sh
set -e
#get the package tarball url
wget `npm view mathjax dist.tarball`
tar xzvf mathjax-*.tgz
cp package/es5/tex-svg-full.js static/js/mathjax-tex-svg-full.js
rm -rf mathjax-*.tgz package

# commit to git
git add .
git commit
```

## Update `exampleSite` demo site

Run [publish-to-gh-pages.sh](publish-to-gh-pages.sh)

# Acknowledgments
[Docsy](https://github.com/google/docsy) inspired layout for this theme.
[Overleaf](https://www.overleaf.com/) examples for LaTeX

Theme built with:
* [Spectrum CSS](https://opensource.adobe.com/spectrum-css/) open-source implementation of Spectrum, Adobe’s design system.
* [Coral Spectrum](https://opensource.adobe.com/coral-spectrum/dist/documentation/) JavaScript library of Web Components following Spectrum design patterns.
* [Markdeep diagrams](https://casual-effects.com/markdeep/features.md.html#diagramexamples)
* [Mermaid](http://mermaid-js.github.io/mermaid/) a Javascript based diagramming and charting tool
* [Fusejs](https://fusejs.io/) a lightweight fuzzy-search in JavaScript
* [Swagger UI](https://swagger.io/tools/swagger-ui/) UI for visualizing APIs written in [OpenAPI Specification](http://spec.openapis.org/oas/v3.0.3)
* [klakegg/hugo](https://github.com/klakegg/docker-hugo) minimal Docker images for Hugo with batteries included
* [Stork](https://stork-search.net/) Impossibly fast web search, made for static sites
* [mark.js](https://markjs.io/) JavaScript keyword highlighter
* [MathJax](https://www.mathjax.org/) Beautiful and accessible math in all browsers

# Contributing

Contributions are welcomed! Read the [Contributing Guide](./.github/CONTRIBUTING.md) for more information.

# Licensing

This project is licensed under the Apache V2 License. See [LICENSE](LICENSE) for more information.
