# Use minimal Alpine image
FROM alpine:3.18

# Install required packages
RUN apk add --no-cache git unzip bash

# Set working directory inside the container (will be bind-mounted)
WORKDIR /mnt/host

# At runtime, clone, unzip, and copy files to /mnt/host
ENTRYPOINT ["/bin/sh", "-c", "\
  git clone https://github.com/LennardEc/nokia_case_study.git /tmp/nokia_case_study && \
  unzip /tmp/nokia_case_study/data/Trace/trace.csv.zip -d /tmp/nokia_case_study/data/Trace/ && \
  mkdir -p /mnt/host/data/Formula /mnt/host/data/Signature /mnt/host/data/Trace && \
  cp -r /tmp/nokia_case_study/data/Formula/* /mnt/host/data/Formula/ && \
  cp -r /tmp/nokia_case_study/data/Signature/* /mnt/host/data/Signature/ && \
  cp /tmp/nokia_case_study/data/Trace/trace.csv /mnt/host/data/Trace/ && \
  cp /tmp/nokia_case_study/instructions.txt /mnt/host/ && \
  echo 'Setup complete. Files written to /mnt/host' \
"]