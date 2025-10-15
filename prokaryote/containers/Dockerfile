FROM ubuntu:22.04

# Prevents some interactive prompts during installs
ENV DEBIAN_FRONTEND=noninteractive

# Update and install basic packages

RUN apt-get update && apt-get install -y \ 
    gawk\
    tabix\
    wget\
    curl\
    bash\
    unzip\
    git\
    python3\
    python3-pip\
    && apt-get clean

# Install python libraries
RUN pip install snakemake pulp==2.7.0
RUN pip install pandas

# Set the default shell to bash
SHELL ["/bin/bash", "-c"]

# Set working directory
RUN useradd -ms /bin/bash rnaseq
USER rnaseq
WORKDIR /home/rnaseq

# Set entrypoint
CMD [ "/bin/bash" ]