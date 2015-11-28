#Using baked base
FROM surajx/dockyard:python-base

#Creating directory for django application source code
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

#Copying django-app source to container
COPY ./django-app /usr/src/app

#Install os packages needed for app
RUN apt-get update && apt-get install -y \
    gcc \
    gettext \
    postgresql-client libpq-dev \
    --no-install-recommends && rm -rf /var/lib/apt/lists/*

#Expose port 8880 of container
EXPOSE 8880

#Installing app requirements
RUN pip install --no-cache-dir -r requirements.txt
