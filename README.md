# Clingo Lessons

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/vsoch/clingo-lessons/main)

Are you interested in learning Answer Set Programming (ASP), specifically
with [clingo](https://github.com/potassco/clingo) ? I am too,
but I learn best by interacting with code, and most of the learning materials:

 - [A User's Guide...](http://wp.doc.ic.ac.uk/arusso/wp-content/uploads/sites/47/2015/01/clingo_guide.pdf)
 - [UT Austin Programming with Clingo](https://www.cs.utexas.edu/~vl/teaching/378/pwc.pdf)
 
This repository provides a Docker container that will build a container
with [Jupyter](https://jupyter.org/) and clingo, and then notebooks
that you can use to learn clingo. If you have a notebook example
that you'd like to contribute, please don't hesitate to [open an issue](https://github.com/vsoch/clingo-lessons/issues)
to either discuss contributing directly, or pointing me to the source so I
can add it.

## Getting Started

You can either use the bindr link at the top of the post to get interactive notebooks
in your browser, or create a local environment on your host. If the first,
then click the link and navigate to the folder with notebooks of interest.
Otherwise, keep reading.

### Local Notebooks

If you want to run notebooks locally, you need to first clone the repository:

```bash
$ git clone git@github.com:vsoch/clingo-lessons
$ cd cling-lessons
```

If you don't have Docker installed, [do that first](https://docs.docker.com/get-docker/).
Then build the container:

```bash
$ docker build -f Dockerfile.clingo -t clingo-lessons .
```

The Dockerfile is named with a prefix only so bindr doesn't automatically
detect it and try to build (it instead uses the [environment.yml](environment.yml)
and [postBuild](postBuild). You'll then want to run the container, binding port 8888 to your host so you
can see jupyter.

```bash
$ docker run --rm --name clingo-lessons -p 8888:8888 -v $PWD/:/home/jovyan/work clingo-lessons
```

At that point, copy the link in your termal to open your browser to [http://localhost:8888](http://localhost:8888)
with the provided token to see folders with notebooks. You can open any notebook to do the interactive tutorial.
If at any point you want to shell into the running container, you can type the
following in another terminal:

```bash
$ docker exec -it clingo-lessons bash
```

If you have any questions or would like to contribute a lesson or example,
please [open an issue](https://github.com/vsoch/clingo-lessons/issues). I'll be adding
examples from the documentation slowly over time as a side project.
