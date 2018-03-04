FROM pennmush-base:latest
MAINTAINER admin@beleriand.middleearth.net

EXPOSE 4739

RUN echo bust5
RUN cd /home/bele && \
    git clone https://github.com/beleriand-mush/deployment.git Beleriand && \
    mkdir -p Beleriand/game/save && \
    echo "tail -f log/*.log" >> Beleriand/game/restart

COPY Beleriand-Files/*.cnf /home/bele/Beleriand/game/
COPY Beleriand-Files/data/* /home/bele/Beleriand/game/data/
COPY Beleriand-Files/log/* /home/bele/Beleriand/game/log/
COPY Beleriand-Files/save /home/bele/Beleriand/game/

CMD ["/home/bele/Beleriand/game/restart"]
