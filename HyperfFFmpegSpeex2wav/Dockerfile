FROM hyperf/hyperf:latest
LABEL maintainer="LW放下" version="1.0" license="MIT"

COPY ./DepFiles/ld-musl-x86_64.so.1 /lib
COPY ./DepFiles/libz.so.1.2.11 /lib
COPY ./DepFiles/libmp3lame.a /usr/local/lib
COPY ./DepFiles/libmp3lame.la /usr/local/lib
COPY ./DepFiles/libmp3lame.so.0.0.0 /usr/local/lib
COPY ./DepFiles/ffmpeg /usr/local/bin
COPY ./DepFiles/libspeex.a /usr/local/lib
COPY ./DepFiles/libspeex.la /usr/local/lib
COPY ./DepFiles/libspeex.so.1.5.1 /usr/local/lib
COPY ./DepFiles/speex2wav /usr/local/bin/

RUN set -ex \
    && ls -al /tmp/ \
    && chmod +x /usr/local/bin/ffmpeg \
    && chmod +x /usr/local/bin/speex2wav \
    && ln -s /usr/local/lib/libmp3lame.so.0.0.0 /usr/local/lib/libmp3lame.so.0 \
    && ln -s /usr/local/lib/libmp3lame.so.0.0.0 /usr/local/lib/libmp3lame.so \
    && ln -s /usr/local/lib/libspeex.so.1.5.1 /usr/local/lib/libspeex.so \
    && ln -s /usr/local/lib/libspeex.so.1.5.1 /usr/local/lib/libspeex.so.1 \
    && cd /tmp/ \
    && ffmpeg -version \
    && php -v \
    && php -m \
    && rm -rf /tmp \
    && echo -e "\033[42;37m Build Completed :).\033[0m\n"

WORKDIR /hyperf-skeleton/