# apicurio-best-practices

This projecti is the source used to publish https://www.apicur.io/apicurio-best-practices/.

## Contributing
If you want to modify/fix an existing guide just open a pr against this repo. Heach pr is built and the preview site archive is attacched to the pr checks to be inspected if needed. When merged to the `main` branch [a github action](https://github.com/Apicurio/apicurio-best-practices/blob/main/.github/workflows/publish.yml) should take care to publish it to githug pages committing the processed asciidoc file to https://github.com/Apicurio/[`gh-pages` branch](apicurio-best-practices/tree/gh-pages).

### Building a local preview
To build a local preview you need `asciidoc` installed. Then run:
```
make clean build
```
this will create a `localpreview/` folder containing the rendered html files. 

If you have `xdg-open` installed (on linux it should be by default) you can open the preview in a browser directly with:
```
make open-preview
```
if you are on mac try `open ./localpreview/index.html`, otherwise simply open `./localpreview/index.html` in your browser of choice.

### Add a new guide
Start from copying `template.adoc` file in `docs/` folder and rename it as needed. Link it into `docs/README.adoc` where appropriate, like:
```
[...]
== New Guide Title

=== xref:new-guide.adoc[My new guide!]
[...]
```
If your guid needs examples or examples projects you can put them into `examples/` folder and reference them accordingly.
