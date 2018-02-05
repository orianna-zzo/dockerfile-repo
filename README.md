# dockerfile-repo

* [hugo-docker](hugo-docker): docker for hugo    
* [alpine-bash-docker](alpine-bash-docker): alpine docker using bash instead of ash    
* [datascience-python-docker](datascience-python-docker): docker for data science in python

## Diagram


blockdiag {
  orientation = portrait;
  default_fontsize = 8;
  A [label="Alpine"];

  A -> alpine-bash;
  alpine-bash -> datascience-python;
  alpine-bash -> hugo-dev;
}