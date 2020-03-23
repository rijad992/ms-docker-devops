FROM node:12


RUN apt-get update \
  && apt-get install -y --no-install-recommends \
libz-dev \
    libpq-dev \
    libssl-dev \
    libmcrypt-dev \
    libicu-dev \
    libxml2-dev \
    curl \
    git \
    zip \
    unzip \
    libzip-dev \
    vim \
    nano \
    wget \
    zsh \
    ruby \
    ruby-dev \
    ruby-bundler \
    ssh-client \
    iputils-ping \
  && rm -rf /var/lib/apt/lists/*

###########################################################################
# Install angular cli:
###########################################################################
RUN npm install -g @angular/cli



###########################################################################
# Set Timezone
###########################################################################

ARG TZ=UTC
ENV TZ ${TZ}

RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone


# Clean up
RUN apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/* && \
    rm /var/log/lastlog /var/log/faillog

# Set default work directory
WORKDIR /var/www/front