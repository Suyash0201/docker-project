# Use the latest Ubuntu image as the base
FROM ubuntu:latest

# Label the Docker image
LABEL image="frontendstatic"

# Install necessary packages, clean up to reduce image size
RUN apt update && \
    apt install -y apache2 unzip && \
    rm -rf /var/www/html/index.html

# Copy the zip file to the container
COPY traffic_light.zip /var/www/html/traffic_light.zip

# Set the working directory
WORKDIR /var/www/html

# Unzip and move files, then clean up
RUN unzip traffic_light.zip && \
    mv traffic_light/* . && \
    rmdir traffic_light && \
    rm -rf traffic_light.zip

# Expose port 80
EXPOSE 80

# Run Apache in the foreground
CMD ["apachectl", "-D", "FOREGROUND"]
