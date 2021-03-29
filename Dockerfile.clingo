FROM jupyter/base-notebook

# This is from: https://github.com/stephsamson/clingo-notebook/blob/main/Dockerfile

ENV PYTHONDONTWRITEBYTECODE=true
EXPOSE 8888

RUN conda install -c potassco clingo

RUN echo 'alias_magic clingo script -p "clingo --no-raise-error"' \
    >> `ipython locate profile`/startup/config.ipy

WORKDIR /home/jovyan/work
CMD ["jupyter", "notebook", "--no-browser", "--ip=0.0.0.0"]
