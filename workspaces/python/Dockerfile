FROM archlinux:latest

RUN --mount=type=cache,target=/var/cache/pacman \
  pacman -Syu --noconfirm 
RUN --mount=type=cache,target=/var/cache/pacman \
  pacman -S --noconfirm python git tailscale openssh && \
  pacman -S --noconfirm npm

RUN npm install -g n && \
  n install lts && \
  npm install -g http-server

RUN ssh-keygen -A
RUN useradd -m -s /bin/bash terence && \
    echo 'terence:terence' | chpasswd
CMD [ "/usr/lib/systemd/systemd","/bin/bash"]

ENTRYPOINT [ "/bin/bash","-c","tailscaled & /usr/sbin/sshd -D" ]
