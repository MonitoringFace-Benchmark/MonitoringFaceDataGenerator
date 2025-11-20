# Use a lightweight base image
FROM alpine:latest

# Set working directory
WORKDIR /app

# Create folder structure
RUN mkdir -p test/data/1 test/data/2 \
    && touch test/instruction

# By default, just keep the container running (optional)
CMD ["sleep", "infinity"]