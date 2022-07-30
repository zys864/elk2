FROM alpine

RUN sed -i 's/dl-cdn.alpinelinux.org/mirrors.tuna.tsinghua.edu.cn/g' /etc/apk/repositories &&\
    apk --update add python py-pip && \
    pip install elasticsearch-curator==3.4.0

# add tasks scripts
ADD ./tasks /etc/periodic/daily
RUN chmod a+x /etc/periodic/daily/*

CMD ["crond", "-f", "-l", "8"]
