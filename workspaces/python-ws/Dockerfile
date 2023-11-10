FROM archlinux:latest

RUN pacman -Syu --noconfirm
RUN pacman -S python git npm --noconfirm

RUN pacman -S npm --noconfirm && npm install -g n && n install lts && npm install -g http-server

CMD [ "/usr/bin/bash"]