FROM scratch
ADD http://ftp.jaist.ac.jp/pub/raspberrypi/raspbian_lite/archive/2020-02-14-13:49/root.tar.xz /

ENV LANG ja_JP.UTF-8

RUN apt update \
 && apt install autoconf \
                bison \
                build-essential \
                libssl-dev \
                libyaml-dev \
                libreadline6-dev \
                zlib1g-dev \
                libncurses5-dev \
                libffi-dev \
                libgdbm6 \
                libgdbm-dev \
                libdb-dev \
                libsodium-dev \
                libopus-dev \
                ca-certificates \
 && wget https://yt-dl.org/downloads/latest/youtube-dl -O /usr/local/bin/youtube-dl \
 && chmod a+rx /usr/local/bin/youtube-dl

USER pi

WORKDIR /home/pi

ENV PATH /home/pi/local/ruby-2.6.6:/home/pi/local/aquestalkpi:/home/pi/local/bin:$PATH

RUN mkdir -p local \
 && cd local \
 && wget https://www.a-quest.com/cgi-bin/download.php?download=1&readed=yes \
 && tar -xvf aquestalkpi-20130827.tgz \
 && rm aquestalkpi-20130827.tgz \
 && git clone https://github.com/rbenv/ruby-build.git \
 && PREFIX=/home/pi/local ./ruby-build/install.sh \
 && ruby-build install 2.6.6 /home/pi/local/ruby-2.6.6

WORKDIR /home/pi

RUN git clone voicebot-repo

WORKDIR /home/pi/repo-name

CMD ["bundle", "exec", "ruby", "main.rb"]






