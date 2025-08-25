FROM python:3.13-slim

# Container-friendly defaults
ENV PYTHONUNBUFFERED=1 \
    PYTHONDONTWRITEBYTECODE=1 \
    PIP_DISABLE_PIP_VERSION_CHECK=1 \
    PIP_NO_CACHE_DIR=1 \
    LANG=C.UTF-8 \
    LC_ALL=C.UTF-8

# System deps (minimal)
RUN apt-get update && apt-get install -y --no-install-recommends \
      git ca-certificates bash-completion curl \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /workspaces

# Copy requirement file early for build cache
COPY .devcontainer/requirements.txt /tmp/requirements.txt

# Install uv + Python packages from requirements.txt
RUN pip install -U pip uv && \
    uv pip install --system -r /tmp/requirements.txt && \
    # enable bash completion for `oj` if installed
    register-python-argcomplete oj > /etc/bash_completion.d/oj || true

# Enable bash completion globally
RUN echo 'if [ -f /etc/bash_completion ]; then . /etc/bash_completion; fi' >> /etc/bash.bashrc

COPY .devcontainer/Dockerfile /docker/Dockerfile
RUN chmod -R 755 /docker

CMD ["bash"]
