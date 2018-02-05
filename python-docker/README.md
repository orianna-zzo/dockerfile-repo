# dockerfile-repo

## Datascience-python-docker
The docker image for data science in Python.
Here are the python packages in this image:
```
# util
wheel
sqlalchemy 
h5py 
tables 
protobuf 
xlrd
xlwt
xlsxwriter
pyyaml
joblib
beautifulsoup4  # HTML/XML parser
dill  # Extends python’s pickle module

# math
numpy
pandas
sympy  # Computer algebra system

# accelerate
cython 
numexpr  # Fast numerical expression evaluator for NumPy
numba  # Compile Python code & speed up code

# graph
bokeh 
seaborn 
matplotlib

# tool
jupyter 
ipywidgets  # IPython HTML widgets for Jupyter
vincent  # Visualization

# ml
sklearn 
scipy 
scikit-learn 
scikit-image 
statsmodels
```

### Get the image
You can get the image from Docker Hub or you can build it with Dockerfile

#### From Docker Hub

```shell
$ docker pull orianna/datascience-python
```

##### Supported tags
* 0.1 latest (base image: ubuntu:16.04)
  h5py & mkl cannot be installed on alpine.


#### From Dockerfile
You can build it from the Dockerfile.

```shell
$ docker build -t your-image-name:your-tag .
```





