# Installation and Setup #

Make sure you have Python 3 installed on your system. If you don't have it, you can download it from the [official Python website](https://www.python.org/downloads/).

## Installing SpaCy ##

```bash
pip install spacy
```

After installing SpaCy, download the Swedish language model.

```bash
python -m spacy download sv_core_web_sm
```

## Installing Polyglot ##

```bash
pip install polyglot
```

Polyglot relies on some additional dependencies that need to be installed separately. Install the following packages:

```bash
pip install PyICU
pip install pycld2
pip install morfessor
```

Now, download the Swedish language Polyglot data.

```bash
polyglot download LANG:sv
```
