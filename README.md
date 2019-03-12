# uWSGI docker image
Docker image with Python and uWSGI.
## Description
It's a very simple image, built from official Python image. It just installs uWSGI and add uwsgi user.
## How to use
Create your Dockerfile from this image:
```
FROM mdafanasev/python-uwsgi:python3.7

# Install your requirements
COPY ./requirements.txt /usr/src/app/
RUN pip install -r /usr/src/app/requirements.txt

# Copy your code
COPY ./project_name /usr/src/app/

# Run uwsgi
USER uwsgi
CMD ["uwsgi","--ini","/path/to/your/uswgi.ini"]
```
