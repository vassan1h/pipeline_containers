FROM mambaorg/micromamba:latest

COPY --chown=$MAMBA_USER:$MAMBA_USER trimgalore_env.yml /trimgalore_env.yml

RUN micromamba install -y -n base -f /trimgalore_env.yml && micromamba clean --all --yes

USER root

# for nf trace
RUN apt-get update && apt-get install -y procps && rm -rf /var/lib/apt/lists/*

USER $MAMBA_USER

ENV PATH "$MAMBA_ROOT_PREFIX/bin:$PATH"