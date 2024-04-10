# Use the official CentOS 7 image as the base image
FROM centos:7

# Install required packages
RUN yum install -y net-tools screen wget mailx jq git unzip

# Set the Terraform version
ARG TERRAFORM_VERSION="1.7.5"

# Download and install Terraform
RUN wget -q -O /tmp/terraform.zip "https://releases.hashicorp.com/terraform/${TERRAFORM_VERSION}/terraform_${TERRAFORM_VERSION}_linux_amd64.zip" && \
    unzip /tmp/terraform.zip -d /usr/local/bin && \
    rm /tmp/terraform.zip
    
# Set the working directory in the container
WORKDIR /app

# Copy the script to print the welcome message and Terraform version
COPY script.sh /app/script.sh

# Make the script executable
RUN chmod +x /app/script.sh

# Expose port 5000 to the outside world
EXPOSE 5000

# Run the script when the container starts
CMD ["/app/script.sh"]