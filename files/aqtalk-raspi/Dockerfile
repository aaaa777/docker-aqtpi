FROM scratch
ADD http://ftp.jaist.ac.jp/pub/raspberrypi/raspbian_lite/archive/2020-02-14-13:49/root.tar.xz /

RUN apt update && apt install ca-certificates \
 && wget -p /usr/local/ https://www.a-quest.com/cgi-bin/download.php?download=1&readed=yes \
 && tar -xvf /usr/local/aquestalkpi-20130827.tgz \
 && rm /usr/local/aquestalkpi-20130827.tgz

USER pi

ENV PATH /usr/local/aquestalkpi:$PATH

WORKDIR /home/pi

CMD ["AquesTalkPi"]