# Stage 1: Build Stage
FROM ubuntu:20.04 AS builder

# Install Apache and create index.html
RUN apt-get update \
    && DEBIAN_FRONTEND=noninteractive apt-get install -y apache2 \
    && echo "Hello, Docker! This is Apache running in a Docker container." > /var/www/html/index.html \
    && chown -R www-data:www-data /var/www/html \
    && chmod -R 755 /var/www/html

# Stage 2: Production Stage
FROM ubuntu:20.04

# Copy Apache and index.html from the builder stage
COPY --from=builder / /

# Expose port 80
EXPOSE 80/tcp

# Start Apache service
CMD ["apache2ctl", "-D", "FOREGROUND"]
