FROM continuumio/miniconda3

# Copy environment file
COPY deseq2_env.yml /tmp/deseq2_env.yml

# Create the environment
RUN conda env create -f /tmp/deseq2_env.yml && conda clean -a -y

# Set path to use conda R
ENV PATH /opt/conda/envs/deseq2_env/bin:$PATH
ENV CONDA_DEFAULT_ENV=deseq2_env

# Install msigdbdf properly inside the conda env
RUN /bin/bash -c "source activate deseq2_env && Rscript -e \"install.packages('msigdbdf', repos='https://igordot.r-universe.dev')\""

# Default command
CMD [ "R" ]
