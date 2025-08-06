FROM continuumio/miniconda3

# Copy environment file into the container
COPY deseq2_env.yml /tmp/deseq2_env.yml

# Create the environment
RUN conda env create -f /tmp/deseq2_env.yml && conda clean -a -y

# Install R packages inside the conda R
RUN conda run -n deseq2_env Rscript -e "install.packages('msigdbdf', repos=c('https://igordot.r-universe.dev', 'https://cloud.r-project.org'))"

# Set PATH (so that RUN and CMD use conda R)
ENV PATH /opt/conda/envs/deseq2_env/bin:$PATH

# Default command
CMD ["R"]
