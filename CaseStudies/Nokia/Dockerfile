FROM alpine:3.18

RUN apk add --no-cache git unzip bash
WORKDIR /data

ENTRYPOINT ["/bin/sh", "-c", "\
git clone https://github.com/LennardEc/nokia_case_study.git /tmp/nokia_case_study && \
unzip /tmp/nokia_case_study/data/Trace/trace.csv.zip -d /tmp/nokia_case_study/data/Trace/ && \
mkdir -p /data/data/Formula /data/data/Signature /data/data/Trace && \
cp -r /tmp/nokia_case_study/data/Formula/* /data/data/Formula/ && \
cp -r /tmp/nokia_case_study/data/Signature/* /data/data/Signature/ && \
cp /tmp/nokia_case_study/data/Trace/trace.csv /data/data/Trace/ && \
cp /tmp/nokia_case_study/instructions.txt /data/ && \
echo 'Setup complete. Files written to /data'"
]