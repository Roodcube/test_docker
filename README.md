# test_docker


#*****************
# Deven Rood
# CS2080
# 11/21/22
#*****************

FROM ubuntu

RUN apt update && apt install -y zsh curl

RUN curl -fsSL https://code-server.dev/install.sh | sh

RUN useradd -m -u 8877 nonroot

USER nonroot

CMD code-server --auth none --bind-addr 0.0.0.0:8080


#***********************
# Run command:
#
# docker run -it -p 80:8080 --name rood-code-server rood-lab12
#***********************
