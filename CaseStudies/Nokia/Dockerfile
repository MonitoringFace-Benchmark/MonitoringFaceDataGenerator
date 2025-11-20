FROM alpine:3.18
RUN apk add --no-cache git bash unzip


WORKDIR /tmp

RUN git clone https://github.com/LennardEc/nokia_case_study.git
RUN unzip /tmp/nokia_case_study/data/Trace/trace.csv.zip -d /tmp/nokia_case_study/data/Trace/


WORKDIR /mnt/host
RUN mkdir -p data/Formula data/Signature data/Trace \
    && cp -r /tmp/nokia_case_study/data/Formula/* data/Formula/ \
    && cp -r /tmp/nokia_case_study/data/Signature/* data/Signature/ \
    && cp /tmp/nokia_case_study/data/Trace/trace.csv data/Trace/ \
    && cp /tmp/nokia_case_study/instructions.txt .

CMD ["echo", "Setup complete. Exiting."]