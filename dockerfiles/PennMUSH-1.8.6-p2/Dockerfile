FROM pennmush-base:latest
MAINTAINER admin@beleriand.middleearth.net

RUN git clone https://github.com/pennmush/pennmush.git /mush/pennmush && \
        cd /mush/pennmush && \
        git checkout 186p2 && \
        ./configure --prefix=`pwd`/dist && \
        make && \
        cp src/netmud game/netmush && \
        cp src/info_slave game/info_slave && \
        cp src/ssl_slave game/ssl_slave
RUN cd /mush/pennmush && \
        git checkout master && \
        cd dbtools && \
        cmake -DCMAKE_BUILD_TYPE=Release . && \
        make
