# notebook
Simple template for compiling a set of markdown files into nice looking notebooks using pandoc.

## Requirements
The notebook requires an installation of [pandoc](https://pandoc.org/installing.html) and the additonal filter [pandoc-crossref](https://github.com/lierdakil/pandoc-crossref).

## Usage
Clone the `notebook` repository into the folder containing the markdown documents.
The `index.yml` file within contains the `pandoc` options for compiling markdown files into the desired output format.
Add the markdown filenames to the ``input-file`` option in the desired order and give the notebook a title using the ``metadata->title``.
Finally, run the command 

```terminal
pandoc -d notebook/index.yml
```

in the directory of markdown files and the compiled notebook is saved in a folder `output`. 

## Output Options
The `index.yml` controls the output options of the resulting notebook.
Here the filename and location of the output file can be adjusted using the option `output-file`.
The option `to` controls the output format.
Per default a PDF file of the notebook is generated using one of the included styles via the ``metadata-file`` option.
The behavior of the `pandoc` command can be customized using further options.

## Notebook Styles
The repository provides some default designs and design elements for styling the notebooks.
Per default the notebook is exported as PDF file in book format.

### Styles
YAML files with layout and typesetting metadata for specific output types.
The styles can be chosen in ``index.yml`` using the ``metadata-file`` option and customized to suite individual needs.
Current styles inlude:

- `pdf/booklet-singlepage.yml`
  
  A PDF notebook in book format.
  Each markdown file constitutes a separate chapter, and a bibliography is inserted if `citeproc` is utilized.
  
- `pdf/booklet-doublepage.yml`

  Same as `pdf-singlepage.yml` but with binding corrections for alternating pages.
  Ideal for printing and binding the notebook.

### Citation-Styles
An assortment of different publicly available citation styles for the `citeproc` filter.

### Templates
Custom pandoc templates used for the respective output format when the `standalone` option is set to `true` (default).
The template is specified using the `template` option.
