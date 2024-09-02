# We are placing a base for our Docker image
FROM ubuntu:latest

# We are labeling our Docker image here
LABEL image="frontendstatic"

# Update package list and install required packages in one layer
RUN apt update && \
    apt install -y apache2 unzip && \
    rm -rf /var/www/html/index.html

# Copy the source code from local storage to the container
COPY counter/*/var/www/html/

# Set the working directory
WORKDIR /var/www/html

# Optionally unzip if needed (uncomment if there are .zip files to unzip)
# RUN unzip yourfile.zip

# Expose port 80 to the outside world
EXPOSE 80

# Provide the container with a process
CMD ["apachectl", "-D", "FOREGROUND"]
