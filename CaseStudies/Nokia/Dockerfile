FROM alpine:latest
RUN apk add --no-cache git unzip bash
WORKDIR /mnt/host

CMD mkdir -p data/Formula data/Signature data/Trace && \
    git clone https://github.com/LennardEc/nokia_case_study.git /tmp/nokia_case_study && \
    unzip /tmp/nokia_case_study/data/Trace/trace.csv.zip -d /tmp/nokia_case_study/data/Trace/ && \
    cp -r /tmp/nokia_case_study/data/Formula/* data/Formula/ && \
    cp -r /tmp/nokia_case_study/data/Signature/* data/Signature/ && \
    cp /tmp/nokia_case_study/data/Trace/trace.csv data/Trace/ && \
    cp /tmp/nokia_case_study/instructions.txt .
