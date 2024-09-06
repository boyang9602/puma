FROM ignaciovizzo/puma

ENV DATASETS=/data/
RUN mkdir -p $DATASETS

# Install some utils in case you run the container interactively
RUN apt-get update && apt-get install --no-install-recommends -y \
    curl \
    git \
    silversearcher-ag \
    tree \
    vim \
    && rm -rf /var/lib/apt/lists/*

# Add user to share files between container and host system
ARG USER_ID
ARG GROUP_ID

RUN addgroup --gid $GROUP_ID user
RUN adduser --disabled-password --gecos '' --uid $USER_ID --gid $GROUP_ID user
USER user

