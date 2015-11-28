#Using baked base
FROM surajx/dockyard:python-base

#Creating directory for django application source code
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

#Install os packages needed for app
RUN apt-get update && apt-get install -y \
    gcc \
    git \
    ssh \
    gettext \
    postgresql-client libpq-dev \
    --no-install-recommends && rm -rf /var/lib/apt/lists/*

#Adding verfication key
RUN mkdir -p /root/.ssh && \
    touch /root/.ssh/known_hosts && \
    ssh-keyscan github.com >> /root/.ssh/known_hosts

#Cloning latest django-app
RUN git clone git@github.com:devwf/django-app.git /usr/src/app

#Expose port 8880 of container
EXPOSE 8880

#Installing app requirements
RUN pip install --no-cache-dir -r requirements.txt
