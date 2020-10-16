# pandoc-plantuml-filter

Pandoc filter which converts PlantUML code blocks to PlantUML images.

````md
```plantuml
Alice -> Bob: Authentication Request
Bob --> Alice: Authentication Response

Alice -> Bob: Another authentication Request
Alice <-- Bob: another authentication Response
```
````

## Usage

Install it with pip:

```sh
pip install git+https://github.com/MyriaCore/pandoc-plantuml-filter.git
```

And use it like any other pandoc filter:

```
pandoc tests/sample.md -o sample.pdf --filter pandoc-plantuml
```

The PlantUML binary must be in your `$PATH` or can be set with the
`PLANTUML_BIN` environment variable.

### Additional parameters

You could pass additional parameters into `plantuml` filter which will be processed as picture's options:

````md
```{ .plantuml height=50% plantuml-filename=test.png }
Alice -> Bob: Authentication Request
Bob --> Alice: Authentication Response
```
````

The `plantuml-filename` parameter create a symlink for the destination picture, which could be used in the same file as an image directly.
