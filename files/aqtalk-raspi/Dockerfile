FROM scratch
ADD http://ftp.jaist.ac.jp/pub/raspberrypi/raspbian_lite/archive/2020-02-14-13:49/root.tar.xz /

WORKDIR /usr/local/

RUN wget https://www.a-quest.com/cgi-bin/download.php?download=1&readed=yes \
 && tar -xvf aquestalkpi-20130827.tgz \
 && rm aquestalkpi-20130827.tgz

USER pi

ENV PATH /usr/local/aquestalkpi:$PATH

CMD ["AquesTalkPi"]