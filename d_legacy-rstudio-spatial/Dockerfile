FROM rocker/rstudio:3.4.2
ENV RANG_PATH /rang.R
COPY rang.R /rang.R
RUN echo "deb http://archive.debian.org/debian stretch main contrib non-free" > /etc/apt/sources.list
RUN apt-get update -qq \
	&& apt-get install -y libpcre3-dev zlib1g-dev pkg-config libcurl4-openssl-dev \
	&& apt-get install -y gdal-bin libgdal-dev libproj-dev
RUN Rscript $RANG_PATH
EXPOSE 8787
CMD ["/init"]
