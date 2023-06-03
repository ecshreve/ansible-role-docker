FROM ecshreve/devbox

RUN useradd -m eric -s /usr/bin/fish \
  && usermod -aG docker,sudo,adm eric \
  && echo "eric:password" | chpasswd \
  && echo "eric ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers.d/eric \
  && mkdir -p /workspaces \
  && chown -R eric:eric /workspaces \
  && chown -R eric:eric /home/eric

USER eric

RUN curl -Lks https://raw.githubusercontent.com/ecshreve/figgy/main/install | /bin/sh

