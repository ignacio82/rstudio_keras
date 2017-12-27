FROM rocker/tidyverse
LABEL maintainer="Ignacio Martinez <ignacio@protonmail.com>"

RUN apt-get -y --no-install-recommends install \
    python-setuptools python-dev build-essential
    
RUN easy_install pip

RUN pip install --upgrade virtualenv

RUN install2.r --error \
    corrplot ggthemes caret partykit randomForest e1071 pander keras
    
RUN R -e "library(keras); install_keras()"

## clean up    
RUN rm -rf /tmp/downloaded_packages/ /tmp/*.rds
