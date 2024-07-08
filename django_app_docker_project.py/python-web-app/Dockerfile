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
    pip3 install watchdog && \
    pip3 install -r requirements.txt --break-system-packages && \
    cd devops

#error- if you won't add watchdog then you container proccess execution will get stuck and shows watching for file changes with statReloader(only in django based application)
# cd devops is main app where all code exists
#devops is project  name which we created using django skelton command

ENTRYPOINT ["python3"] 
# ENTRYPOINT is something which cannot be overwrite

#this cmd needs to run the django application
CMD ["manage.py", "runserver", "0.0.0.0:8000", "--reload"]
# CMD values contains which can be overwrite again
# 0.0.0.0:8000 is reprsenting port where container will be running

