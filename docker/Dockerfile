FROM ubuntu:latest

RUN apt-get update && apt-get install -y build-essential curl \
libffi-dev libffi7 libgmp-dev libgmp10 \
libncurses-dev libncurses5 libtinfo5

ENV BOOTSTRAP_HASKELL_NONINTERACTIVE=1

#RUN curl https://downloads.haskell.org/~ghcup/x86_64-linux-ghcup > /usr/bin/ghcup && \
#	chmod +x /usr/bin/ghcup && \
#	ghcup install ghc 8.6.5 && \
#	ghcup set ghc 8.6.5 && \

RUN sh -c "curl -sSL https://get.haskellstack.org/ | sh"

ENV PATH ~/.ghcup/bin:$PATH
RUN sh -c "curl --proto '=https' --tlsv1.2 -sSf https://get-ghcup.haskell.org | sh"
