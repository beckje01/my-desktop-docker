FROM node

# Tell debconf to run in non-interactive mode
ENV DEBIAN_FRONTEND noninteractive

RUN apt-get update && apt-get install -y \
	apt-transport-https \
	ca-certificates \
	curl \
	gnupg \
	--no-install-recommends


# Install dependencies
RUN apt-get update && apt-get install -y \
	gconf2 \
	gconf-service \
	gvfs-bin \
	libasound2 \
	libcap2 \
	libgconf-2-4 \
	libgtk2.0-0 \
	libnotify4 \
	libnss3 \
	libxkbfile1 \
	libxss1 \
	libxtst6 \
	libx11-xcb-dev \
	xdg-utils \
	--no-install-recommends \
	&& rm -rf /var/lib/apt/lists/*


RUN git clone https://github.com/geeeeeeeeek/electronic-wechat.git && cd electronic-wechat && npm install
RUN cd /electronic-wechat && npm run build:linux
# docker run -it  --entrypoint /bin/sh beckje01/wechat
ENTRYPOINT [ "/electronic-wechat/dist/electronic-wechat-linux-x64/electronic-wechat" ]
