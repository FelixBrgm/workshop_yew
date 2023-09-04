FROM rust

RUN apt-get update && \
    apt-get install git -y && \
    apt-get install curl -y

RUN rustup target add wasm32-unknown-unknown

RUN cargo install --locked trunk

RUN git clone https://github.com/FelixBrgm/.dotfiles.git ~/.unix

RUN cd ~/.dotfiles && \
    chmod 777 ./setup.sh && \
    ./setup.sh

CMD ["tail", "-f", "/dev/null"]
