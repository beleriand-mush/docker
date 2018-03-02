FROM pennmush:1.8.6-p2
MAINTAINER admin@beleriand.middleearth.net

EXPOSE 4739

USER bele

COPY Beleriand-Files /mush/beleriand
RUN cd /mush/pennmush && \
        gzip -cd ../beleriand/data/indb.gz | \
        ./dbtools/dbupgrade | \
        gzip -c > game/data/indb.gz
RUN cd /mush/pennmush && \
        gzip -cd ../beleriand/data/outdb.gz | \
        ./dbtools/dbupgrade | \
        gzip -c > game/data/outdb.gz
RUN cd /mush/pennmush/game && \
    cp mush.cnf mush-orig.cnf && \
    echo "compress_program gzip" >> mush.cnf && \
    echo "uncompress_program gunzip" >> mush.cnf && \
    echo "compress_suffix .gz" >> mush.cnf && \
    echo "money_singular Penny"  >> mush.cnf && \
    echo "money_plural Pennies" >> mush.cnf && \
    cp restart.dst restart && \
    echo "log tail -f log/*" >> restart && \
    cp -r ../../beleriand/txt/* txt/ && \
    cp ../../beleriand/log/* log/ && \
    cp ../../beleriand/Beleriand.cnf . && \
    cp ../../beleriand/access.cnf . && \
    cp ../../beleriand/names.cnf .

CMD ["/mush/pennmush/game/restart"]
