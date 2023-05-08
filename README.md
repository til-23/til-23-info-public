## Build the documentation website files locally

Install dependencies (recommended: install within a python virtual environment - [here's a tutorial](https://realpython.com/python-virtual-environments-a-primer/#create-it))
```
pip install sphinx sphinx-autoapi sphinx-rtd-theme
```

Build the html docs into the '_build' folder, based on source files from 'source' folder
```
sphinx-build -b html source _build 
```

After building webpages from source, you can now view the docs at `_build/index.html`, by opening the file in a browser.

## Editing the Sphinx docs source
Edit the ``.rst`` source files in the 'source/' directory.

### reST syntax Cheatsheet
https://github.com/ralsina/rst-cheatsheet/blob/master/rst-cheatsheet.rst


## Configure Sphinx
You can edit the ``conf.py`` file in the 'source/' directory to configure how Sphinx interprets source files and outputs/renders files.
You can also add extensions to add custom behaviours to Sphinx. 

References:
1. https://www.sphinx-doc.org/en/master/usage/configuration.html
2. https://www.sphinx-doc.org/en/master/usage/quickstart.html



## Hosting the web pages
For an easy and free way to host the docs online, deploying with Github Pages is an easy option.

Tutorial: https://coderefinery.github.io/documentation/gh_workflow/

**Please test the website _locally_ before pushing to the remote `main` branch.**
