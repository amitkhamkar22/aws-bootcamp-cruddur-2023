FROM python:3.10-slim-buster

# Inside the container
# Make a new folder called backend -flask
WORKDIR /backend-flask

# first requirement file is from outside the container and secong will be created inside the container
# The requiremets.txt files gets copied for current directory on your local machine to the docker to install libraries to run the application
COPY requirements.txt requirements.txt

# Inside the container 
# Install the python libraries used by the app
RUN pip3 install -r requirements.txt

#outside the container to inside the container
# The first . means everything in the /backend-flask directory on local machine
# the second . means /backend-flask folder inside the container
COPY . .

# Set environment variable inside the container when container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}

#Command
# python3 -m -flask run --host=0.0.0.0 --posrt=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]