FROM        ghcr.io/parkervcp/yolks:debian

LABEL       author="Nils Gereke" maintainer="mail@wuffy.eu"

LABEL       org.opencontainers.image.source="https://github.com/pterodactyl/yolks"
LABEL       org.opencontainers.image.licenses=MIT

RUN         apt update \
				&& apt upgrade -y \
				&& apt install -y libfaudio0 xfce4
RUN             echo xfce4-session >~/.xsession
RUN             useradd -m -d /home/container container



USER        containerENV
ENV         USER=container HOME=/home/container
WORKDIR     /home/container

COPY        ./entrypoint.sh /entrypoint.sh
CMD         [ "/bin/bash", "/entrypoint.sh" ]
