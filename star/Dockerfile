FROM mambaorg/micromamba:latest

COPY --chown=$MAMBA_USER:$MAMBA_USER star_env.yml /star_envyml

RUN micromamba install -y -n base -f /star_env.yml && micromamba clean --all --yes

USER root

# for nf trace
RUN apt-get update && apt-get install -y procps && rm -rf /var/lib/apt/lists/*

USER $MAMBA_USER

ENV PATH "$MAMBA_ROOT_PREFIX/bin:$PATH"