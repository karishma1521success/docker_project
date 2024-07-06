FROM ubuntu
#base image 

# setting app directory as working directory for image
WORKDIR /app

#copying host file to image file system (app)
COPY requirements.txt /app
COPY devops /app

#Install necessary packages for python application as we have ubunut base image not python based image
RUN apt-get update && \
    apt-get install -y python3 python3-pip && \
    pip install -r requirements.txt && \
    cd devops

# cd devops is main app where all code exists

ENTRYPOINT [ "python3" ] 
# ENTRYPOINT is something which cannot be overwrite

#this cmd needs to run the django application
CMD [ "manage.py", "runserver", "0.0.0.0:8000" ]
# CMD values contains which can be overwrite again
# 0.0.0.0:8000 is reprsenting port where container will be running

