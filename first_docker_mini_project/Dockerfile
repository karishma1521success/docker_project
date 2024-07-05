FROM ubuntu:latest
# set the base os image

# set the working directory in the image
WORKDIR /app

# copy the files from the host file system to the image file system
COPY . /app/

# Install necessary packages
RUN apt-get update && apt-get install -y python3 python3-pip
# neccessary packages for python based app

# set environment variables
ENV Name World

#Run a command  to start the application
CMD [ "python3" , "app.py" ]

