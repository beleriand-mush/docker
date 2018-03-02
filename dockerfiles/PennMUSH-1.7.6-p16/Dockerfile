FROM pennmush-base:latest
MAINTAINER admin@beleriand.middleearth.net

RUN apt-get install -y curl
RUN mkdir /mush && \
	cd /mush && \
	curl -O http://download.pennmush.org/Source/oldsrc/1.7/pennmush-1.7.6p16.tar.gz && \
	tar xvfz pennmush-1.7.6p16.tar.gz
