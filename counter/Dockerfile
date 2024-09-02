# Use the official Nginx image from the Docker Hub
FROM nginx:alpine

# Copy the HTML, CSS, and JavaScript files to the Nginx server directory
COPY . /usr/share/nginx/html

# Expose port 80 to the outside world
EXPOSE 80

# Start Nginx server
CMD ["nginx", "-g", "daemon off;"]
