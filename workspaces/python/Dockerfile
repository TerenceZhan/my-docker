FROM archlinux:latest

RUN pacman -Syu --noconfirm
RUN pacman -S python --noconfirm
RUN pacman -S git --noconfirm
RUN pacman -S npm --noconfirm
RUN pacman -S tailscale --noconfirm

RUN npm install -g n && \
  n install lts && \
  npm install -g http-server

CMD [ "/usr/lib/systemd/systemd","/bin/bash"]

ENTRYPOINT [ "/bin/bash","-c","tailscaled" ]
