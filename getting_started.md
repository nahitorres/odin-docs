---
layout: default
title: Getting Started
nav_order: 1
---

# {{page.title}} with Odin
{: .mb-6}

## Getting Started with Docker

1. Download <a href="https://github.com/rnt-pmi/odin" target="_blank">Odin</a> from the GitHub repository.
2. Go to the odin folder you have just downloaded:
```
  cd path/to/odin
```

3. Build the _odin_ image from the _Dockerfile_:
```
  docker build -t odin .
```

4. Run the container:
```
  docker run -it -p 8888:8888 odin
```

5. Go to the folder 'home/examples' from the <a href="https://jupyter.org/" target="_blank">Jupyter Notebook</a> and try the ready-to-use notebooks.

## Getting Started with Virtual Environment

1. Download <a href="https://github.com/rnt-pmi/odin" target="_blank">Odin</a> from the GitHub repository.
2. Go to the odin folder you have just downloaded:
```
  cd path/to/odin
```

3. Create a virtual environment:
```
  python -m venv venv
```
4. Activate the virtual environment just created:
- On MacOS/Linux:
```
  source venv/bin/activate
```
- On Windows:
```
  .\venv\Scripts\activate
```
5. Install the framework and its requirements:
```
  pip install -e . --user
```
6. N.B. To be able to use the meta-annotation extractor, two more packages need to be installed (tensorflow and mtcnn). Simply execute the following command:
```
  pip install tensorflow mtcnn
```
7. Start a <a href="https://jupyter.org/" target="_blank">Jupyter Notebook</a>, go to the folder 'examples' and try the ready-to-use notebooks.
