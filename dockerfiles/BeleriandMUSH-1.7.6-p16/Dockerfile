FROM pennmush:1.7.6-p16
MAINTAINER admin@beleriand.middleearth.net

EXPOSE 4739

COPY Beleriand-Files /mush/beleriand-old
RUN cd /mush && \
	mkdir beleriand && \
	cp -r pennmush/game/* beleriand && \
	cp -r beleriand-old/txt/* beleriand/txt && \
	cp -r beleriand-old/save/* beleriand/save && \
	cp -r beleriand-old/data/* beleriand/data && \
	cp -r beleriand-old/log/* beleriand/log && \
	cp beleriand-old/Beleriand.cnf beleriand/ && \
	cp beleriand-old/access.cnf beleriand/ && \
	cp beleriand-old/names.cnf beleriand/ && \
	cp beleriand-old/restart beleriand/
CMD ["/mush/beleriand/restart"]
