FROM ubuntu:latest

ARG USERNAME=dev
ARG USER_UID=1000
ARG USER_GID=$USER_UID

# Create the user
RUN groupadd --gid $USER_GID $USERNAME \
    && useradd --uid $USER_UID --gid $USER_GID -m $USERNAME \
    #
    # [Optional] Add sudo support. Omit if you don't need to install software after connecting.
    && apt-get update \
    && apt-get install -y sudo \
    && echo $USERNAME ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/$USERNAME \
    && chmod 0440 /etc/sudoers.d/$USERNAME

# ********************************************************
# * Anything else you want to do like clean up goes here *
# ********************************************************

# [Optional] Set the default user. Omit if you want to keep the default as root.
USER $USERNAME

RUN sudo apt-get update && sudo apt-get install -y build-essential git curl

ENV BOOTSTRAP_HASKELL_NONINTERACTIVE=1

ENV PATH /root/.cabal/bin:/root/.ghcup/bin:~/.ghcup/bin:$PATH
RUN sh -c "curl --proto '=https' --tlsv1.2 -sSf https://get-ghcup.haskell.org | sh"
