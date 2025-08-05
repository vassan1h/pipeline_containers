FROM continuumio/miniconda3

# Copy environment file into the container
COPY deseq2_env.yml /tmp/deseq2_env.yml

# Create the environment
RUN conda env create -f /tmp/deseq2_env.yml && conda clean -a -y

# Set PATH
ENV PATH /opt/conda/envs/deseq2_env/bin:$PATH

# Default command
CMD ["R"]