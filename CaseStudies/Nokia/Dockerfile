FROM alpine:3.18
RUN apk add --no-cache git bash


WORKDIR /tmp

RUN git clone https://github.com/LennardEc/nokia_case_study.git
RUN unzip /tmp/nokia_case_study/data/Trace/trace.csv.zip -d /tmp/nokia_case_study/data/Trace/


WORKDIR /mnt/host

# Copy the relevant folders/files from the cloned repo
COPY --from=0 /tmp/nokia_case_study/data/Formula /mnt/host/data/Formula
COPY --from=0 /tmp/nokia_case_study/data/Signature /mnt/host/data/Signature
COPY --from=0 /tmp/nokia_case_study/data/Trace /mnt/host/data/Trace
COPY --from=0 /tmp/nokia_case_study/instructions.txt /mnt/host/instructions.txt

CMD ["echo", "Setup complete. Exiting."]