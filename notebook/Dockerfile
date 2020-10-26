FROM python:3.7-slim-stretch

RUN mkdir /notebook \
    && mkdir /notebook/notes

ENV PYTHONPATH=${PYTHONPATH}:${PWD}

# Install GCC, Make and libpq-dev (for psicopg)
RUN apt-get update \
    && apt-get install -y gcc libpq-dev make

#Upgrade pip
RUN pip3 install --upgrade pip

# Install Postgres Client
RUN mkdir -p /usr/share/man/man1 \
    && mkdir -p /usr/share/man/man7 \
    && apt-get install -y postgresql-client

# Install Poetry
RUN pip3 install poetry

COPY pyproject.toml /notebook/

WORKDIR /notebook

# Install Dependencies
RUN poetry config virtualenvs.create false \
    && export PYTHON_KEYRING_BACKEND=keyring.backends.null.Keyring \
    && poetry install --verbose -vvv