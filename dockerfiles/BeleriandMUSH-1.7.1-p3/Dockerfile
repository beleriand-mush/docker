FROM pennmush-base:latest
MAINTAINER admin@beleriand.middleearth.net

EXPOSE 4739

RUN echo bust4
RUN cd /root && \
    git clone https://github.com/beleriand-mush/deployment.git Beleriand && \
    mkdir -p Beleriand/game/save && \
    echo "tail -f log/*.log" >> Beleriand/bin/restart

COPY Beleriand-Files/*.cnf /root/Beleriand/game/
COPY Beleriand-Files/data/* /root/Beleriand/game/data/
COPY Beleriand-Files/log/* /root/Beleriand/game/log/
COPY Beleriand-Files/save /root/Beleriand/game/

CMD ["/root/Beleriand/game/restart"]
