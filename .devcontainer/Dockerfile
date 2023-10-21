FROM ubuntu:latest

RUN apt-get update && apt-get install -y build-essential git curl

ENV BOOTSTRAP_HASKELL_NONINTERACTIVE=1

ENV PATH /root/.cabal/bin:/root/.ghcup/bin:~/.ghcup/bin:$PATH
RUN sh -c "curl --proto '=https' --tlsv1.2 -sSf https://get-ghcup.haskell.org | sh"
