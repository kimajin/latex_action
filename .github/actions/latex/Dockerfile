ARG VARIANT="focal"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    curl \
    python3 \
    latexmk \
    lmodern \
    texlive \
    texlive-latex-extra \
    texlive-lang-japanese \
    && rm -rf /var/lib/apt/lists/*

RUN mktexlsr && mkdir -p /app
WORKDIR /app

ADD entrypoint.sh /entrypoint.sh
RUN ["chmod", "+x", "/entrypoint.sh"]
ENTRYPOINT ["/entrypoint.sh"]
