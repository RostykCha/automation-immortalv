# automation-immortalv
 Immortalv automation tests


How to run?

docker pull selenium/standalone-chrome

docker run -d -p 4445:4444 -v /dev/shm:/dev/shm selenium/standalone-chrome

docker build .


version: '3'  # Version of the Docker Compose file format

services:
service_name:
image: <image_name>  # Docker image for the service
build:  # Custom build options for the service
context: <path>  # Build context (directory containing Dockerfile)
dockerfile: <Dockerfile_path>  # Path to the Dockerfile (optional)
args:  # Build-time arguments (optional)
- ARG_NAME=value
labels:  # Custom labels (optional)
- "label_name=value"
command: <command>  # Override the default command
environment:  # Environment variables for the service
- VAR_NAME=value
volumes:  # Volume bindings for the service
- <host_path>:<container_path>:<mode>
ports:  # Port mapping for the service
- "<host_port>:<container_port>"
expose:  # Expose ports without publishing them to the host
- <container_port>
networks:  # Network connections for the service
- <network_name>
depends_on:  # Specify dependencies on other services
- <service_name>
healthcheck:  # Define a health check for the service
test: <test_command>
interval: <interval>
timeout: <timeout>
retries: <retries>
logging:  # Logging options for the service
driver: <driver>
options:
key: value

volumes:
volume_name:
driver: <driver_name>  # Volume driver to use (optional)
external: <true/false>  # Use an external volume (optional)
driver_opts:  # Driver-specific options (optional)
key: value

networks:
network_name:
driver: <driver_name>  # Network driver to use (optional)
external: <true/false>  # Use an external network (optional)
driver_opts:  # Driver-specific options (optional)
key: value

configs:
config_name:
file: <path>  # Path to the configuration file

secrets:
secret_name:
file: <path>  # Path to the secret file

