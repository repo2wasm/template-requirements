# Python environment with a requirements.txt

[![repo2wasm](https://img.shields.io/badge/any_text-launch-F37626?logo=jupyter&label=Jupyter)](https://repo2wasm.github.io/template-requirements)

[![Binder](http://mybinder.org/badge_logo.svg)](http://mybinder.org/v2/gh/binder-examples/requirements/HEAD)

A repo compatible with `repo2wasm` and mybinder.org using a `requirements.txt` as configuration file.

Access the live version of this repo at

- [GitHub Pages](https://repo2wasm.github.io/template-requirements)
- [mybinder.org](http://mybinder.org/v2/gh/repo2wasm/template-requirements/HEAD)

## Notes
The `requirements.txt` file should list all Python libraries that your notebooks
depend on, and they will be installed using:

```
pip install -r requirements.txt
```

The base Binder image contains no extra dependencies, so be as
explicit as possible in defining the packages that you need. This includes
specifying explicit versions wherever possible.

If you do specify strict versions, it is important to do so for *all*
your dependencies, not just direct dependencies.
Strictly specifying only some dependencies is a recipe for environments
breaking over time.

If the root requirements.txt for some reason doesn't align with the dependencies 
you need in your Binder environment, you can create a `requirements.txt` file in 
a `.binder` folder that will take precedent!

[pip-compile](https://github.com/jazzband/pip-tools/) is a handy
tool for combining loosely specified dependencies with a fully frozen environment.
You write a requirements.in with just the dependencies you need
and pip-compile will generate a requirements.txt with all the strict packages and versions that would come from installing that package right now.
That way, you only need to specify what you actually know you need,
but you also get a snapshot of your environment.

In this example we include the library `seaborn` which will be installed in
the environment, and our notebook uses it to plot a figure.
