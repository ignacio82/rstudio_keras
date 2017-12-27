FROM rocker/tidyverse
LABEL maintainer="Ignacio Martinez <ignacio@protonmail.com>"

## Python dependencies
RUN apt-get update && apt-get -y upgrade
RUN apt-get install python-pip python-virtualenv -y
RUN pip install virtualenv

## R packages
RUN R -e "install.packages(c('corrplot', 'ggthemes', 'caret', 'partykit', 'randomForest', 'e1071', 'pander'), repos = 'https://cloud.r-project.org')"
RUN R -e "install.packages('devtools', repos = 'https://cloud.r-project.org')"
RUN R -e "devtools::install_github('rstudio/tensorflow')"
RUN R -e "devtools::install_github('rstudio/keras')"
RUN R -e "keras::install_keras()"

## clean up    
RUN rm -rf /tmp/downloaded_packages/ /tmp/*.rds