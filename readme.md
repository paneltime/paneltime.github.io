# README for paneltime GitHub Pages (`paneltime.sitegen` and `paneltime.github.io`)

## paneltime.sitegen

`paneltime.sitegen` contains the Quarto source files used to generate the
`paneltime.github.io` website.

The website is not built directly from either of these repositories.

Generation and deployment are handled by:

```text
paneltime/setup_script.py
```

which uses the Quarto configuration in:

```text
paneltime/qmd/_quarto.yml
```

The configuration contains:

```yaml
output-dir: ../../paneltime.github.io
```

which renders the generated HTML directly into the sibling
`paneltime.github.io` repository.

## Build workflow

Expected directory structure:

```text
parent/
├── paneltime/
│   ├── setup_script.py
│   └── qmd/
├── paneltime.github.io/
└── paneltime.sitegen/
```

Generate the website and set up the project:

```bash
cd paneltime
python setup_script.py
```

Generate and push all repositories:

```bash
python setup_script.py -g
```

Do NOT edit generated HTML in `paneltime.github.io` manually.

Edit the Quarto `.qmd` files instead.
