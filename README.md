# Clingo Docker

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

If you don't have Docker installed, [do that first](https://docs.docker.com/get-docker/).
Then build the container:

```bash
$ docker build -f Dockerfile.clingo -t clingo-lessons .
```

You'll then want to run the container, binding port 8888 to your host so you
can see jupyter.

```bash
$ docker run --rm --name clingo-lessons -p 8888:8888 -v $PWD/:/home/jovyan/work clingo-lessons
```

At that point, open your browser to [http://localhost:8888](http://localhost:8888)
to see folders with notebooks. You can open any notebook to do the interactive tutorial.
If at any point you want to shell into the running container, you can type the
following in another terminal:

```bash
$ docker exec -it clingo-lessons bash
```
