# python image based on layers after SCRATCH which is the empty docker image
FROM python:3.10-slim-buster

# make new directory in the container 
WORKDIR /backend-flask

# copy req into the container
COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt

# copy everything into the container
COPY . .

# set env vars
ENV FLASK_ENV=development

EXPOSE ${PORT}
# Command to run the code
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]

# remove the docker container once loaded
# docker run --rm -p 4567:4567 -it -e FRONTEND_URL='*' -e BACKEND_URL='*' backend-flask
# docker run --rm -p 4567:4567 -it  -e FRONTEND_URL -e BACKEND_URL backend-flask
# unset FRONTEND_URL="*"
# unset BACKEND_URL="*"